# Iniciando um projeto node com Typescript 

`yarn init -y`
`yarn add -D typescript` (adicionando o ts de forma local)

`yarn add express`
`code .`

criar o boilerplate express em src > index.ts

`A tipagem por padrão não ocorrerá com typescript: com JS o próprio VsCode se encarrega de instalar por trás dos panos`

`yarn add @types/express -D`     // em produção não existe typescript

// para rodar o servidor: node src/index.ts (erro: o node não entende typescript, então precisaremos converter .ts para .js)

`yarn tsc src/index.ts`

ainda teremos erro graças ao "default" do arquivo js (ESModuleInterop deverá ser instalado):

`yarn tsc --init` e `yarn tsc`

// tsconfig.json será criado e corrigirá o erro do import

vamos separar o arquivo index.js do index.ts alterando o tsconfig.json em outDir:

"outDir" : "./dist" ou "./build"    // cria uma pasta com os .js

vamos instalar o TS-NODE-DEV para criar um compilador rápido em tempo real parecido com o nodemon:

`yarn add ts-node-dev -D`

no package.json:
	scripts: {
		"dev:server": "ts-node-dev --respawn --transpileOnly src/index.ts"
	}
