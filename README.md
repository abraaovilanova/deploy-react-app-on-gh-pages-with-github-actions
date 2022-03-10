
# Como fazer o deploy de um React app no GitHub Pages usando o GitHub Actions

Clique [Aqui!](https://abraaovilanova.github.io/deploy-react-app-on-gh-pages-with-github-actions) para ver a aplicação!

## Deploy de um React app no GitHub Pages
Neste pequeno tutorial, mostrarei como você pode criar um aplicativo React e fazer o deploy do seu projeto no GitHub Pages.

Para criar o aplicativo React é preciso usar o comando `npx create-react-app`, para implantar o aplicativo React, nos usaremos a biblioteca `gh-pages`, que é um pacote `npm` que podemos usar para implantar coisas no GitHub Pages.

Se você seguir este tutorial, você terá um novo aplicativo React—hospedado no GitHub Pages—que você pode personalizar.

### 1. Criando um Aplicativo React
Para criar uma aplicação React use o seguinte comando:

```bash
npx create-react-app <my-app>
```

entre no repositório criado utilizando:

```bash
    cd <my-app>
```

### 2. Instalando o gh-pages npm package

Agora nos precisamos instalar o `gh-pages`.

```bash
    npm install gh-pages --save-dev
```

Neste ponto, o pacote `gh-pages` npm está instalado em seu computador e a dependência do aplicativo React em relação a ele está documentada no arquivo `package.json` do aplicativo React.

### 3. Add a propriedade homepage no arquivo `package.json`

Abra o arquivo `packege.json` e adicione a propriedade homepage nesse formato: `https://{username}.github.io/{repo-name}`

```json
    {
    "name": "my-app",
    "version": "0.1.0",
    + "homepage": "https://gitname.github.io/react-gh-pages",
    "private": true,
    ...

```

### 4. Add deployment scripts to the package.json file
Abra o arquivo `packege.json` novamente e adicione a seguinte propriedade no script:
```json
"scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
```

### Deploy o Aplicativo React para o GitHub Pages
```bash
    npm run deploy
```

## Configurando o GitHub Actions
...

## :books: Referências
* [React Deployment](https://create-react-app.dev/docs/deployment/#github-pages)
* [About Deploying a React App (created using create-react-app) to GitHub Pages](https://github.com/gitname/react-gh-pages)
* [How to Deploy React App to GitHub Page](https://www.c-sharpcorner.com/article/how-to-deploy-react-application-on-github-pages/)
* [Setting up a CI/CD workflow on GitHub Actions for a React App (with GitHub Pages and Codecov)](https://dev.to/dyarleniber/setting-up-a-ci-cd-workflow-on-github-actions-for-a-react-app-with-github-pages-and-codecov-4hnp)