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

## Fluxo geral da aplicação
1. O servidor Express responde `GET/` com `public/pages/index.html`.
2. Os arquivos estáticos são servidos em `/assets` (`main.css`e `main.js`).
3. No navegador, o usuário digita um CEP e pressiona `Enter`.
4. O Javascript  remove todos os caracteres não numéricos (`replace(/\D/g,""))`.
5. Se o resultado não tiver 8 digítos, exibe o erro.
6. Se tiver 8 digítos, exibe estado de carregamento e faz `fetch` no ViaCEP.
7. A interface mostra erro (`response. ok === false` ou `data.erro`) ou sucesso com os dados retornados.
8. Quando o input fica vazio, o resultado é limpo.

   
## Explicação das funções do `main.js`
Arquivo: `public/assets/js/main.js` 

*`showResult(message, type)`*
- Atualiza `#result` com HTML (`innerHTML`).
- Aplica classe CSS dinâmica (`result error`, `result loading`, `result sucess`).

  *`handleCepSerach()`*
fluxo implementado

1. Lê o valor do input e normaliza para apenas digítos.
2. Valida tamanho de 8 dígitos.
3. Exibe `"Consultando CEP...`.
4. Fez `GET https://viacep.com.br/ws/{cep}/json/.`
5. Se `response.ok` for falso, exibe `"Falha no serviço"`
6. Se `data.erro` vier verdadeiro, exibe `"CEP não encontrado"`.
7. Caso contrário, monta o HTML de sucesso com:
   - CEP
   - Logradouro
   - Complemento
   - Bairro
   - Cidade
   - UF
   - Estado
   - Região
   - DDD
##Eventos registrados
`input.addEventListener("keydown",...)`
- Ao pressionar `Enter`, chama `handleCepSearch()`.

`input.addEvent Listener("input",...)`
- Se o campo ficar vazio (após `trim()` , limpa `#result` e restaura a classe base.
  
  
