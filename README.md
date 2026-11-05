# Willian Oliveira — Personal Trainer

Site de apresentação do Willian Oliveira, com opções de personal presencial e consultoria online, áreas preparadas para planos, depoimentos, perguntas frequentes e contato.

## Visualização local

O site é estático. Para abrir localmente, sirva a pasta `dist` com um servidor HTTP, por exemplo:

```sh
python3 -m http.server 8000 --directory dist
```

Acesse `http://localhost:8000`.

## Deploy na Vercel

O projeto tem `vercel.json` apontando `dist` como diretório de saída, sem build.

```sh
npx vercel --prod
```

Ou importe o repositório na Vercel (Framework Preset "Other"); as configurações vêm do `vercel.json`.

## Conteúdo de exemplo (vai mudar)

Planos (frequência, local, duração e valores) e depoimentos estão com dados mockados, sinalizados no site como exemplo. Substituir pelos dados reais do Willian, com autorização dos alunos para depoimentos e imagens.

Instagram: [@wilianoliveeira](https://www.instagram.com/wilianoliveeira/).
