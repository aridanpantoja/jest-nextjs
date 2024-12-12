<h1 align="center">Configuração de Jest e Testing Library para Next.js 💻</h1> 

<p align="center">
    <b>Este repositório fornece um guia abrangente para integrar Jest e Testing Library em um projeto Next.js.</b>
</p>

<p align="center">
  <a href="https://nextjs.org/" target="_blank">
    <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js" alt="Distintivo Next.js">
  </a>
  <a href="https://reactjs.org/" target="_blank">
    <img src="https://img.shields.io/badge/React-005CFE?style=for-the-badge&logo=react" alt="Distintivo React">
  </a>
  <a href="https://eslint.org/" target="_blank">
    <img src="https://img.shields.io/badge/Jest-c14a09?style=for-the-badge&logo=jest" alt="Distintivo Jest">
  </a>
  <a href="https://prettier.io/" target="_blank">
    <img src="https://img.shields.io/badge/Testing Library-ffffff?style=for-the-badge&logo=testinglibrary" alt="Distintivo Testing Library">
  </a>
</p>

<h2 id="visao-geral-do-projeto">Visão Geral do Projeto 📋</h2>

Este repositório fornece uma configuração para integrar Jest e Testing Library em seu projeto Next.js.

- **Jest**: Framework de testes JavaScript que automatiza e simplifica testes de unidade e integração.
- **Testing Library**: Biblioteca que promove testes de interface focados na experiência do usuário, independente do framework.

<h2 id="primeiros-passos">Primeiros Passos</h2>

Para começar com este projeto, siga os passos abaixo:

### Pré-requisitos

Certifique-se de ter o seguinte:

- **Node.js**: Baixe em [nodejs.org](https://nodejs.org/).
- **npm**, **yarn** ou **pnpm**: Vem com Node.js; para yarn, visite [yarnpkg.com](https://yarnpkg.com/); para pnpm, visite [pnpm.io](https://pnpm.io/pt/).
- **Projeto Next.js**: Crie um novo projeto com o comando: 
  - npm: `npx create-next-app@latest meu-proximo-app`
  - yarn: `yarn create next-app meu-proximo-app`
  - pnpm: `npx create-next-app@latest meu-proximo-app --use-pnpm`

#### 1. Instalar Dependências Necessárias

Usando npm:
```bash
npm install -D jest @types/jest jest-environment-jsdom @testing-library/react @testing-library/dom @testing-library/jest-dom ts-node ts-jest
```
Usando yarn:
```bash
yarn add --dev jest @types/jest jest-environment-jsdom @testing-library/react @testing-library/dom @testing-library/jest-dom ts-node ts-jest
```
Usando pnpm:
```bash
pnpm install -D jest @types/jest jest-environment-jsdom @testing-library/react @testing-library/dom @testing-library/jest-dom ts-node ts-jest
```

#### 2. Configurar Jest e Testing Library
Após instalar as dependências, crie o arquivo `jest.config.ts` com a seguinte configuração:

```ts
import type {Config} from 'jest';
import nextJest from 'next/jest.js'

const createJestConfig = nextJest({
  dir: './',
})

const config: Config = {
  clearMocks: true,
  collectCoverage: true,
  coverageDirectory: "coverage",
  coverageProvider: "v8",
  setupFilesAfterEnv: ['<rootDir>/jest.setup.ts'],
  testEnvironment: "jsdom",
};

export default createJestConfig(config);
```

Em seguida, crie um arquivo `jest.setup.ts` com a seguinte configuração:

```ts
import '@testing-library/jest-dom'
```

Agora, adicione os scripts de teste no `package.json` da seguinte forma:

```json
"scripts": {
    "test": "jest",
    "test:watch": "jest --watch"
},
```

<h2 id="contribuir">Contribua 🚀</h2>

Se quiser contribuir, clone este repositório, crie sua branch de trabalho e mão na massa!

```bash
git clone https://github.com/aridanpantoja/jest-testing-library-nextjs.git
```

```bash
git checkout -b feature/NOME
```

No final, abra um Pull Request explicando o problema resolvido ou recurso criado. Se existir, adicione uma captura de tela das modificações visuais e aguarde a revisão!

### Documentações que podem ajudar

[📝 Como criar um Pull Request](https://www.atlassian.com/br/git/tutorials/making-a-pull-request) |
[💾 Padrão de commit](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)

<h2 id="licenca">Licença 📃 </h2>

Este projeto está sob licença [MIT](./LICENSE)