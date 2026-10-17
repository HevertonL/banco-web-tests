# Banco Web — Testes automatizados com Cypress

Automação de testes da interface de uma aplicação bancária, com foco na validação do fluxo de autenticação.

## Objetivo

Verificar o acesso com credenciais válidas e a mensagem apresentada quando a autenticação falha.

## Cenários implementados

| Cenário | Resultado esperado |
|---|---|
| Login com credenciais válidas | Exibir o título “Realizar Transferência”. |
| Login com credenciais inválidas | Exibir a mensagem “Erro no login. Tente novamente.” |

Os cenários estão em `cypress/e2e/login.cy.js`. Um hook `beforeEach` abre a aplicação antes de cada teste.

## Tecnologias

- JavaScript.
- Cypress — dependência declarada como `^14.5.1`.
- Node.js e npm para instalação e execução.

## Pré-requisitos

- Node.js e npm instalados em versões compatíveis com o Cypress utilizado.
- Aplicação bancária disponível em `http://localhost:4000`.
- Conta de teste compatível com os dados utilizados na suíte.

Este repositório contém os testes. A aplicação bancária deve ser preparada e iniciada separadamente.

## Como executar

Clone o repositório e instale as dependências:

```sh
git clone https://github.com/HevertonL/banco-web-tests.git
cd banco-web-tests
npm ci
```

Executar a suíte sem abrir a interface interativa:

```sh
npm test
```

Executar com o navegador visível:

```sh
npm run cy:headed
```

Abrir a interface interativa do Cypress:

```sh
npm run cy:open
```

## Estrutura

```text
cypress/
  e2e/
    login.cy.js
  fixtures/
  support/
cypress.config.js
package.json
package-lock.json
```

## Ambiente e dados de teste

A URL da aplicação e as credenciais estão definidas diretamente em `login.cy.js`. Para executar em outro ambiente, é necessário ajustar esses valores.

Utilize exclusivamente contas de teste. O estado da aplicação e a disponibilidade da conta influenciam os resultados.

## Escopo atual e próximos passos

A suíte atual valida dois comportamentos de login. Os testes não verificam a execução de transferências.

Melhorias planejadas:

- Configurar a URL por ambiente e externalizar os dados de autenticação.
- Ampliar os cenários de validação do formulário.
- Preparar dados de teste de forma controlada.
- Integrar a execução ao GitHub Actions.
- Publicar evidências de execução.

## Autor

[Heverton Luiz Santos](https://github.com/HevertonL) · [LinkedIn](https://www.linkedin.com/in/heverton-luiz-santos/)
