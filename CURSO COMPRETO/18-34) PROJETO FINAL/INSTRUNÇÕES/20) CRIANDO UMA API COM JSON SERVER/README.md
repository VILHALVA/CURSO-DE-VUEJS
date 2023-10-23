# CRIANDO UMA API COM JSON SERVER
Para criar uma API RESTful simulada usando JSON Server, siga estas etapas:

1. **Instale o JSON Server**: Você precisará ter o JSON Server instalado. Você pode instalá-lo globalmente usando o npm (Node Package Manager) com o seguinte comando:

   ```bash
   npm install -g json-server
   ```

2. **Crie um arquivo JSON para seus dados**: Crie um arquivo JSON que representará seus dados. Por exemplo, você pode criar um arquivo chamado `db.json` e definir alguns dados de exemplo:

   ```json
   {
     "produtos": [
       { "id": 1, "nome": "Produto 1", "preco": 10.99 },
       { "id": 2, "nome": "Produto 2", "preco": 15.99 },
       { "id": 3, "nome": "Produto 3", "preco": 20.99 }
     ]
   }
   ```

3. **Inicie o JSON Server**: Abra um terminal na pasta onde você criou o arquivo `db.json` e inicie o JSON Server usando o seguinte comando:

   ```bash
   json-server --watch db.json
   ```

   Isso iniciará o servidor JSON e disponibilizará sua API em `http://localhost:3000`.

4. **Teste a API**: Você pode acessar e testar sua API usando um cliente HTTP, como o Postman ou o cURL, ou até mesmo usando aplicativos da web ou móveis. Por exemplo, para obter a lista de produtos, você pode fazer uma solicitação GET para `http://localhost:3000/produtos`.

5. **Use a API no seu aplicativo Vue.js**: Agora que você tem uma API JSON simulada, pode usá-la em seu aplicativo Vue.js para buscar, criar, atualizar e excluir dados. Você pode usar bibliotecas como `axios` ou o método `fetch` do navegador para fazer solicitações HTTP para sua API a partir de seu aplicativo Vue.js.

Agora você tem uma API JSON simulada que pode ser usada para testar seu aplicativo Vue.js durante o desenvolvimento. Lembre-se de que o JSON Server é uma ferramenta de desenvolvimento e não é adequado para ambientes de produção. Quando seu aplicativo estiver pronto para implantação em produção, você precisará configurar um servidor e uma base de dados adequados.