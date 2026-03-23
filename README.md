#Atividade 2 - HTTP Request (Consulta de CEP)

## Objetivo 
Construir uma página com **HTML dinâmico + requisição HTTP** para consultar CEPs na API ViaCEP.

## Tecnologia utilizadas
- Node.js
- Express
- dotenv
- HTML/CSS/JavaScript (front-end)
- API pública ViaCEP (`https://viacep.com.br/ws/{cep}/json/`)

## Estrutura do projeto
```text
.
|-- .env
|-- server.js
|-- package.json
|-- public
    |--assets
    |  |--css/main.css
    |  |--js/main.js
    |__pages/index.html
```
## O que cada parte faz?
- `.env`: configuração da porta do servidor (PORT) no caso utilizei 3002
- `server.js` : inicializa o servidor Express, define as rotas e configura a pasta de arquivos estáticos
- `css/main.css` : definicação de estilo e formatação visual da página
- `pages/index.html`: definição da estrutura da página HTML exibida na rota
- `js/main.js`: funcionamento da página, mensagem de erro e visualização dos resutados da API viaCep

##Como executar o projeto
1. Instale as dependências:
`npm install`

2. Inicie o servidor:
`npm start` 

3. Abra o navegador:
`http://localhost:3002`

Caso queira utilizar outra porta, altere `PORT` no arquivo `.env`.

## Modo desenvolvimento
Caso queira rodar o programa com reinício automático ao salvar os arquivos:
`npm dev`
