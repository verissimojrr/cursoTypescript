1. criar uma pasta para o projeto
2. criar arquivo .gitignore, entrar no site www.gitignore.io, buscar node e copiar todo o resultado e colocar no arquivo criado
3. no terminal, dentro do projeto, digitar npm i typescript -D e depois npm i ts-node -D , para colocar nas dependencias de desenvolvimento (obs: tive que instalar globalmente, com o -g, pra funcionar)
4. criar pasta .vscode (para podermos configurar o vscode especificamente para o projeto),  criamos um settings.json, abirmos chaves e colocamos "code-runner.executorMap": {

        "typescript": "npx ts-node --files"
    }
5. depois entrar no terminal e instalar: npm i eslint -D
6. npm i @typescript-eslint/eslint-plugin @typescript-eslint/parser -D
7. cria o arquivo .eslintrcjs na raiz do projeto; se tudo der certo, ao digitar const nome = 'luiz' aparecera um erro no nome
8. instalar o prettier npm i -g prettier eslint-config-prettier eslint-plugin-prettier
9. criar o arquivo .prettierrc.js na raiz da pasta e colar as referencias como estao no repositorio
10. digitar no terminal npx tsc --init (vai criar arquivo tsconfig.json); editar "lib": ["ESNext","DOM"], no arquivo, alem de "outDir": "./dist" e "include": ["./src"] (esta ultima fora de compileroptions)
11. criar uma pasta src e colocar os arquivos ts das aulas la
12. apos a configuracao, tesar no terminal npx tsc...vai criar a pasta dist (com os arquivos para producao)
13. editorconfig: na pasta raiz do projeto, coloca botao direito do mouse e seleciona generate editorconfig e edita: (trim_trailing_whitespace = true
insert_final_newline = true
end_of_line = lf)
14. configurando o webpack: npm i ts-loader webpack webpack-cli -D
15. na raiz do projeto, criar o arquivo webpack.config.js
16. buscar no google webpack typescript, entrar no site deles e copiar o que tem que ser colocado dentro do arquivo webpack.config.ts
17. adiciona devtool: 'source-map', e mode: 'development', (dentro do path: acrescentar=> , 'assets', 'js') no webpack.config.js
18. no entry, modifica o caminho do arquivo index.ts para o que criamos
19. modificar no arquivo tsconfig.json "outDir": "./dist/assets/js",
20. npx webpack no terminal para gerar a pasta dist
21. na pasta dist,  criar o index.html e a pasta css/styles.css
22. adicionar no index html um html simples, com os links para os arquivos style e bundle...colocar uma cor de fundo no style
23. no terminal, digitar npx webpack -w para ele assistir as mudanca realizadas
24. criar a arquivo mod.ts na pasta webpack e colocar: console.log('sou o modulo'), para teste
25. no index.ts, adicionar: import './mod' para vermos o que foi colocado no arquivo mod
26. a configuracao que o professor colocou do webpack e so para trabalho com frontend, se  tiver backend junto, muda...entao ele modificou a pasta dist  para frontend, retornou o arquivo tsconfig.json como estava antes e criou um novo arquivo tsconfigfrontend.json com as configuracoes so para frontend com: "outDir": "./frontend/assets/js",
27. no arquivo webpack.config.js, modificar: rules: [
      {
        test: /\.tsx?$/,
        loader: 'ts-loader',
        exclude: /node_modules/,
        options: {
          configFile: 'tsconfig.frontend.json',
        },
      },
    ],

    e tambem  path: path.resolve(__dirname, 'frontEnd', 'assets', 'js'),
28. no arquivo package.json, incluir nos scripts: "build:frontend": "webpack -w",
    "build:backend": "tsc",
29. o npm  run build:frontend vai acionar o frontend e o npm run build:backend o backend
30. o professor recomenda fazer um projeto pra frontend e outro pra backend


