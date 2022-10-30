# S206 - Qualidade de Software
- Repositório da disciplina Qualidade de Software - S206. 
- Instituto Nacional de Telecomunicações - Inatel. 
- Curso: Engenharia de Software.
- Prof. Christopher Lima

Para acompanhar a parte prática desta disciplina, será necessário utilizar algumas ferramentas para quem utiliza o SO Windows:

## Instalação do ambiente de desenvolvimento:

1. Git Bash (Git for Windows - mais leve)
https://gitforwindows.org/

2. Nodejs (node):
https://nodejs.org/en/

3. IDE VSCode (code):
https://code.visualstudio.com/
OBS: Pode usar qualquer IDE. Eclipse, InteliJ...fica a seu critério.

4. JDK (java):
https://www.oracle.com/java/technologies/javase-downloads.html

5. Maven (mvn)
https://maven.apache.org


## Instalação - Cypress (Teste de UI):
1. Faça a instalação do cypress via linha de comando. Abra o terminal e digite

```
npm install cypress
```

2. Caso não queira utilizar o cypress pelo NPM, pode fazer o download direto do site: https://www.cypress.io/

Link para download direto: https://download.cypress.io/desktop

Basta baixar, extrair, executar o Cypress.exe e apontar para o diretório do projeto desejado na interface do cypress.
Utilize a IDE para editar o código.

### Comandos úteis cypress (utilize a aula para enteder o que cada comando faz):

```
Criar o diretório inicial e indicar para o node que o diretório é um projeto
npm init

Baixar as dependencias do projeto (caso já tenha baixado o código do git)
npm install

Abrir cypress pela linha de comando:
./node_modules/.bin/cypress open

Rodar specs por linha de comando:
./node_modules/.bin/cypress run --spec 'cypress/e2e/**/'

Para gerar um report HTML, siga os 4 passos abaixo:

1. Adicionando as dependências necessárias para gerar o reporte de testes:
npm i --save-dev cypress-mochawesome-reporter
	
2. Modificar o arquivo cypress.config.js:
const { defineConfig } = require('cypress');

module.exports = defineConfig({
  reporter: 'cypress-mochawesome-reporter',
  e2e: {
    setupNodeEvents(on, config) {
      require('cypress-mochawesome-reporter/plugin')(on);
    },
  },
});

3. Adicionar em cypress/support/e2e.js:
import 'cypress-mochawesome-reporter/register';

4. Rodar specs pela linha de comando:
./node_modules/.bin/cypress run --spec 'cypress/e2e/**/'

```
