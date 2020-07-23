```bash
$ yarn init -y
$ yarn add express
$ yarn add -D typescript
$ yarn tsc --init
$ yarn add -D @types/express
$ yarn add -D ts-node-dev
```
> acrescenta isso no package.json
```json
"scripts": {
    "build": "tsc",
    "dev:server": "ts-node-dev --transpileOnly --ignore-watch node_modules src/server.ts",
  }
```
> rodar o servidor ts como o ts-node-dev
```bash
$ yarn dev:server
```
> instalando o Eslint
```bash
$ yarn add eslint@6.8.0 -D
$ yarn eslint --init
```
> escolha as opções abaixo, em sequência
```bash
$ > To check syntax, find problems and enforce code style
$ > Javascript modules (import/export)
$ > None of these
$ > Yes
$ > **Pressione a tecla espaço** e selecione a opção Node
$ > Use a popular style guide
$ > Airbnb
$ > JSON
$ > Escolha "No"
```
```bash
$ yarn add @typescript-eslint/eslint-plugin@latest eslint-config-airbnb-base@latest eslint-plugin-import@^2.21.2 @typescript-eslint/parser@latest -D
```
> criar na raiz do projeto um arquivo .eslintignore, e insere isso dentro dele.
```
/*.js
node_modules
dist
```
> abra o .eslintrc.json, e adicione dentro de "extends" a linha:
```json
"plugin:@typescript-eslint/recommended"
```
> Para que o NodeJS consiga entender arquivos Typescript nas importações pois por padrão vai ser apresentado um erro dizendo que as importações de arquivos Typescript não foram resolvidas, para resolver isso basta instalar uma dependência que habilite essa funcionalidade:
```
$ yarn add eslint-import-resolver-typescript -D
```
> Agora para que essa configuração funcione corretamente vamos adicionar logo abaixo das `"rules"` no `.eslintrc.json` o seguinte:
```json
"settings": {
    "import/resolver": {
      "typescript": {}
    }
  },
"import/extensions": [
    "error",
    "ignorePackages",
    {
      "ts": "never"
    }
  ]
```
> instalação do Prettier
```bash
$ yarn add prettier eslint-config-prettier eslint-plugin-prettier -D
```

> Para resolver os conflitos entre as regras do ESLint e as regras do Prettier vamos criar um arquivo na raiz do projeto como [prettier.config.js]
```js
module.exports = {
  singleQuote: true,
  trailingComma: 'all',
	arrowParens: 'avoid',
}
```
```bash
$ yarn add uuidv4
$ yarn add -D @types/uuidv4
$ yarn add typeorm pg
```

