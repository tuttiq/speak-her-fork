![GitHub](https://img.shields.io/github/license/tuttiq/speak-her-br)
[![Netlify Status](https://api.netlify.com/api/v1/badges/24555378-b065-47de-a170-46c23cb537de/deploy-status)](https://app.netlify.com/sites/speak-her-br/deploys)
![W3C Validation](https://img.shields.io/w3c-validation/html?targetUrl=https%3A%2F%2Fspeak-her-br.netlify.app)

# SpeakHer Brazil

Esse repositório é uma ramificação do projeto japonês:
- https://github.com/WWCodeTokyo/speak-her-db
- https://speakher.jp
- Os créditos pela versão inicial do projeto vão para @ ann-kilzer, @tuttiq e @yanarchy

https://speak-her-br.netlify.app/

SpeakHer BR é um banco de dados de mulheres palestrantes no Brasil. Uma desculpa comum que ouvimos dos organizadores de conferências e eventos é que eles não conseguem encontrar nenhuma mulher. Vamos banir essa desculpa. Junte-se à nossa lista e certifique-se de que as mulheres tenham uma representação justa para palestras em público.

O objetivo de coletar essas informações é para que os organizadores do evento possam pesquisar facilmente por palestrantes e que outros palestrantes possam se conectar e apoiar uns aos outros.

## Como Contribuir:

Por favor verifique nossas [diretrizes para contribuidores](./CONTRIBUTING.md).

## Código de Conduta:

Todos os contribuintes deste repositório devem seguir o [Código de Conduta](./CODE_OF_CONDUCT.md). Obrigado por nos ajudar a construir um projeto de código aberto inclusivo.

## Executando o código:

Requisitos:
- [Yarn](https://yarnpkg.com/)
- Uma [conta Airtable](https://airtable.com) gratuita

### Conexão com o banco de dados:

Este projeto usa Airtable como consulta com o banco de dados.Siga estas etapas para configurar um banco de dados em seu ambiente local:
1. Faça uma cópia de ‘.env.sample’ e renomeie para ‘.env.development’
2. Registre-se como um contribuidor do banco de dados de desenvolvimento Airtable [clicando aqui](https://airtable.com/invite/l?inviteId=invAoJbouvb5C5QZK&inviteToken=c48305a76c153129574835def8f4e34f123722cbe27f1007312091f5e485a160)
3. Obtenha sua chave de API Airtable em sua [conta Airtable](https://airtable.com/account)
4. Obtenha o ID do banco de dados de desenvolvimento no [DB API Docs](https://airtable.com/app5umPHNtFiu2Pns/api/docs#javascript/introduction)
5. Edite ‘.env.development’ para adicionar seu ‘AIRTABLE_API_KEY’ e o desenvolvimento ‘AIRTABLE_DB_ID’

`.env.development`
```
NODE_ENV=development
VUE_APP_AIRTABLE_DB_ID=[dev database ID aqui]
VUE_APP_AIRTABLE_API_KEY=[sua chave de API aqui]
AIRTABLE_DB_ID=[dev database ID aqui]
AIRTABLE_API_KEY=[sua chave de API aqui]
```

Você pode alterar outras configurações do banco de dados em `/plugins/airtable.js`.

Mais informações sobre o esquema do banco de dados e a documentação da consulta [aqui](https://airtable.com/app5umPHNtFiu2Pns/api/docs#javascript/introduction) (faça login com a conta que você registrou na etapa 2).

### Rodando o aplicativo:

```
cd web
yarn serve
```

Acesse-o em `localhost: 8080` em seu navegador.

### Testando a produção em ambiente local
Se você tiver acesso ao banco de dados de produção, pode definir sua configuração de produção em `.env.production` e executar o aplicativo no modo de produção usando o comando `yarn serve --mode production`