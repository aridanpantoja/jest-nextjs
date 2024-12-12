<h1 align="center">Jest and Testing Library Setup for Next.js 💻</h1> 

<p align="center">
    <b>This repository provides a comprehensive guide for integrating Jest and Testing Library into a Next.js project.</b>
</p>

<p align="center">
  <a href="https://nextjs.org/" target="_blank">
    <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js" alt="Next.js Badge">
  </a>
  <a href="https://reactjs.org/" target="_blank">
    <img src="https://img.shields.io/badge/React-005CFE?style=for-the-badge&logo=react" alt="React Badge">
  </a>
  <a href="https://eslint.org/" target="_blank">
    <img src="https://img.shields.io/badge/Jest-c14a09?style=for-the-badge&logo=jest" alt="Jest Badge">
  </a>
  <a href="https://prettier.io/" target="_blank">
    <img src="https://img.shields.io/badge/Testing Library-ffffff?style=for-the-badge&logo=testinglibrary" alt="Testing Library Badge">
  </a>
</p>

<p align="center">
  <i>Read this in other languages: <a href="./translations/README-ptBR.md">Português</a></i>
</p>

<h2 id="project-overview">Project Overview 📋</h2>

This repository provides a setup for integrating Jest and Testing Library into your Next.js project.

- **Jest**: JavaScript testing framework that automates and simplifies unit and integration testing.
- **Testing Library**: Library that promotes user-experience-focused interface testing, independent of the framework.

<h2 id="getting-started">Getting Started</h2>

To get started with this project, follow the steps below:

### Prerequisites

Ensure you have the following:

- **Node.js**: Download from [nodejs.org](https://nodejs.org/).
- **npm**, **yarn** or **pnpm**: Comes with Node.js; for yarn, visit [yarnpkg.com](https://yarnpkg.com/); for pnpm, visit [pnpm.io](https://pnpm.io/pt/).
- **Next.js Project**: Create a new project with the command: 
  - npm: `npx create-next-app@latest my-next-app`
  - yarn: `yarn create next-app my-next-app`
  - pnpm: `npx create-next-app@latest my-next-app --use-pnpm`

#### 1. Install Required Dependencies

Using npm:
```bash
npm install -D jest @types/jest jest-environment-jsdom @testing-library/react @testing-library/dom @testing-library/jest-dom ts-node ts-jest
```
Using yarn:
```bash
yarn add --dev jest @types/jest jest-environment-jsdom @testing-library/react @testing-library/dom @testing-library/jest-dom ts-node ts-jest
```
Using pnpm:
```bash
pnpm install -D jest @types/jest jest-environment-jsdom @testing-library/react @testing-library/dom @testing-library/jest-dom ts-node ts-jest
```

#### 2. Configure Jest and Testing Library
After installing the dependencies, create `jest.config.ts` file with the following configuration:

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

Next, create a `jest.setup.ts` file with the following configuration:

```ts
import '@testing-library/jest-dom'
```

Now, just add the test scripts in the `package.json` as follows:

```json
"scripts": {
    "test": "jest",
    "test:watch": "jest --watch"
},
```

<h2 id="contribute">Contribute 🚀</h2>

If you want to contribute, clone this repo, create your work branch and get your hands dirty!

```bash
git clone https://github.com/aridanpantoja/jest-testing-library-nextjs.git
```

```bash
git checkout -b feature/NAME
```

At the end, open a Pull Request explaining the problem solved or feature made, if exists, append screenshot of visual modifications and wait for the review!

### Documentations that might help

[📝 How to create a Pull Request](https://www.atlassian.com/br/git/tutorials/making-a-pull-request) |
[💾 Commit pattern](https://gist.github.com/joshbuchea/6f47e86d2510bce28f8e7f42ae84c716)

<h2 id="license">License 📃 </h2>

This project is under [MIT](./LICENSE) license