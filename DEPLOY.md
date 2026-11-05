# Guia de deploy — site do Willian (para o Matheus)

Objetivo: publicar o site na **sua** conta da Vercel, ligar ao GitHub (cada push na `main` atualiza o site) e colocar um domínio próprio comprado no Registro.br.

O site é estático (HTML em `dist/`), sem build. O `vercel.json` do repo já tem toda a configuração necessária.

---

## 1. Importar o repo na Vercel (jeito mais fácil, sem CLI)

1. Acesse https://vercel.com/signup e entre com sua conta do **GitHub**.
2. Vá em https://vercel.com/new.
3. Na lista de repositórios, escolha **Willianpersonal**. Se não aparecer, clique em *Adjust GitHub App Permissions* e libere o repo.
4. Clique em **Import** e confira:
   - Framework Preset: **Other**
   - Build Command e Install Command: vazios (o `vercel.json` já cuida disso)
   - Output Directory: `dist`
5. Clique em **Deploy**. Em cerca de 1 minuto o site fica no ar em `https://willianpersonal.vercel.app` (ou parecido).

Depois disso, **todo push na `main` atualiza o site**. Branches e PRs geram links de prévia, sem mexer no site real.

---

## 2. (Opcional) Instalar a CLI da Vercel no Mac

Não é necessária para o deploy acima. Só serve para publicar pelo terminal.

Como você usa o Codex, cole este pedido nele:

> Instale a CLI da Vercel no meu Mac (verifique se Node.js está instalado; se não estiver, instale via Homebrew). Rode `npm i -g vercel`, depois `vercel --version` para confirmar, e por fim `vercel login` para eu autenticar.

Comandos manuais, se preferir:

```sh
brew install node        # só se não tiver Node.js
npm i -g vercel
vercel login
vercel --prod            # na pasta do projeto, publica em produção
```

---

## 3. Comprar o domínio no Registro.br

1. Acesse https://registro.br e clique em **Criar cadastro**. Precisa de CPF ou CNPJ, e-mail e telefone.
2. Na busca, digite o nome desejado (ex.: `willianoliveira.com.br`, `willianpersonal.com.br`) e veja se está livre.
3. Clique em **Registrar**. Você escolhe o período (1 ano costuma custar na faixa de R$ 40, mas confira o valor na tela) e paga por Pix, boleto ou cartão.
4. Confirme o e-mail. O domínio fica ativo logo após o pagamento ser confirmado.

Dica: registre no CPF ou CNPJ de quem vai ser o dono do domínio (Willian ou você). Isso define de quem ele é.

---

## 4. Ligar o domínio ao site

**Se preferir, me chame (Iago) que a gente resolve junto.**

Passo a passo:

1. Na Vercel, abra o projeto → **Settings → Domains** → **Add**.
2. Digite o domínio (ex.: `willianoliveira.com.br`) e adicione também o `www.`. A Vercel mostra quais registros DNS usar.
3. No Registro.br, abra o domínio → **DNS → Alterar servidores DNS**. Há duas formas:
   - **Servidores da Vercel (mais simples):** troque os servidores DNS por `ns1.vercel-dns.com` e `ns2.vercel-dns.com`.
   - **Manter o DNS do Registro.br:** use *Configurar zona DNS* e crie os registros que a Vercel indicou na tela. Em geral, um tipo `A` para o domínio raiz e um `CNAME` para `www`.
4. Volte à Vercel. Quando os registros propagarem, o domínio muda para **Valid Configuration** e o HTTPS é emitido automaticamente.

A propagação do DNS pode levar de alguns minutos até 24–48 horas.

---

## 5. Limpeza

O Iago já fez um deploy de teste na conta dele e vai apagá-lo. Depois que o seu estiver no ar, vale conferir se o link novo abre normalmente.

---

## Pendências de conteúdo

Os planos (valores, local, duração) e os depoimentos estão com **dados de exemplo**, sinalizados no site. Antes de divulgar, substituir pelos dados reais do Willian e conseguir a autorização dos alunos para as fotos e os depoimentos.
