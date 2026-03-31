# npmCI

Projeto de automacao de testes end-to-end com Cypress integrado ao GitHub Actions.

O objetivo e ter um fluxo de npmCI que:
- executa testes automaticamente a cada push
- gera evidencias de execucao para portfolio
- publica screenshots e videos como artifacts no CI

## Stack

- Node.js
- Cypress
- GitHub Actions

## Estrutura do projeto

```text
.
|-- .github/
|   `-- workflows/
|       `-- ci.yml
|-- cypress/
|   |-- e2e/
|   |-- fixtures/
|   |-- screenshots/
|   `-- support/
|-- cypress.config.js
|-- package.json
`-- README.md
```

## Como executar localmente

### 1) Instalar dependencias

Com npm:

```bash
npm install
```

Com yarn:

```bash
yarn install
```

### 2) Rodar testes no modo headless

Com npm/npx:

```bash
npx cypress run --browser electron
```

Com yarn:

```bash
yarn cypress run --browser electron
```

### 3) Rodar em modo interativo (opcional)

```bash
npx cypress open
```

## Pipeline de CI (GitHub Actions)

O workflow em `.github/workflows/ci.yml` executa:

1. checkout do codigo
2. execucao dos testes Cypress
3. upload de screenshots (quando houver falha)
4. upload de videos (sempre)

### Acionamento

- push para o repositorio

### Artifacts gerados

- `cypress-screenshots`
- `cypress-videos`

Para baixar:

1. abra a aba Actions do repositorio
2. entre no run desejado
3. no fim da pagina, baixe os artifacts

## Evidencias para portfolio

Este projeto foi estruturado para gerar material de demonstracao de QA automaticamente:

- screenshots de falhas para demonstrar analise de erro
- videos completos das execucoes para mostrar cobertura e fluxo
- historico de execucoes no GitHub Actions para comprovar automacao continua

### Dica para enriquecer o portfolio

- Inclua no README prints dos runs aprovados
- Mostre um exemplo de falha com screenshot + correcao
- Adicione um pequeno resumo do bug encontrado e como foi validado

## Sobre o projeto

Este repositorio representa um modelo de npmCI focado em qualidade, rastreabilidade e geracao de evidencias de teste para uso profissional em portfolio de QA.
