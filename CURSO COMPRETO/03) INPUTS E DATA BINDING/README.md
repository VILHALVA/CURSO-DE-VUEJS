# INPUTS E DATA BINDING
## CONCEITO:
**Inputs e Data Binding** são conceitos fundamentais no Vue.js e são usados para conectar os dados do modelo (data) a elementos de entrada (inputs) em sua aplicação. Essa conexão permite que os dados sejam atualizados automaticamente quando os elementos de entrada são alterados e vice-versa.

Aqui estão os principais conceitos relacionados a Inputs e Data Binding no Vue.js:

1. **Data Binding (Vinculação de Dados)**: Data Binding é o processo de conectar os dados do modelo (armazenados em objetos Vue) aos elementos da interface do usuário, como inputs, textos, listas, etc. O Vue.js oferece duas maneiras principais de fazer isso:

   - **One-Way Data Binding**: Isso envolve a ligação de dados de um modelo para um elemento da interface do usuário, mas não vice-versa. Isso significa que as alterações no modelo afetam a interface do usuário, mas as alterações na interface do usuário não afetam o modelo diretamente.

   - **Two-Way Data Binding**: Isso envolve a ligação de dados bidirecional, onde as alterações no modelo são refletidas na interface do usuário e vice-versa. No Vue.js, isso é alcançado principalmente com a diretiva `v-model` para inputs, como `<input v-model="message">`.

2. **Diretiva `v-model`**: A diretiva `v-model` é usada para criar data binding bidirecional com inputs HTML. Ela permite que os dados do modelo sejam vinculados ao valor do input e, ao mesmo tempo, qualquer alteração no input é refletida de volta no modelo. Aqui está um exemplo:

   ```html
   <input v-model="message">
   <p>{{ message }}</p>
   ```

   No exemplo acima, o valor do input é vinculado à variável `message`, e qualquer alteração no input atualiza automaticamente a variável `message` e é refletida na tag `p`.

3. **Data no Vue.js**: Os dados são definidos em uma instância Vue usando a propriedade `data`. Por exemplo:

   ```javascript
   new Vue({
     el: '#app',
     data: {
       message: 'Olá, Vue.js!'
     }
   });
   ```

   O objeto `data` contém as variáveis ​​que você deseja vincular à interface do usuário.

4. **Manipulação de Eventos**: Para manipular eventos, como cliques em botões, você pode usar diretivas `v-on`. Por exemplo:

   ```html
   <button v-on:click="doSomething">Clique em mim</button>
   ```

   E no seu Vue.js:

   ```javascript
   new Vue({
     el: '#app',
     data: {
       message: 'Olá, Vue.js!'
     },
     methods: {
       doSomething: function() {
         this.message = 'Evento de clique acionado!';
       }
     }
   });
   ```

   Nesse exemplo, o método `doSomething` é chamado quando o botão é clicado, e ele atualiza a variável `message`.

5. **Computed Properties**: Você pode usar computed properties para realizar cálculos com base nos dados do modelo e retornar um valor calculado. Essas propriedades computadas são reativas e são atualizadas automaticamente sempre que as dependências mudam.

   ```javascript
   new Vue({
     el: '#app',
     data: {
       firstName: 'John',
       lastName: 'Doe'
     },
     computed: {
       fullName: function() {
         return this.firstName + ' ' + this.lastName;
       }
     }
   });
   ```

   Neste exemplo, `fullName` é uma propriedade computada que combina o `firstName` e o `lastName`.

O Data Binding é um dos recursos mais poderosos do Vue.js, tornando a construção de interfaces de usuário interativas e dinâmicas muito mais fáceis. Ele simplifica a sincronização de dados entre o modelo e a interface do usuário, economizando tempo e esforço no desenvolvimento de aplicativos web.

## FORMULARIO:
Vou explicar como criar um formulário com inputs e demonstrar como usar o Data Binding para capturar os valores desses inputs em uma instância Vue. 

**1. Crie um formulário no seu HTML:**

```html
<div id="app">
  <form @submit.prevent="submitForm">
    <label for="name">Nome:</label>
    <input type="text" id="name" v-model="name">
    
    <label for="email">E-mail:</label>
    <input type="email" id="email" v-model="email">
    
    <button type="submit">Enviar</button>
  </form>

  <div>
    <p>Nome digitado: {{ name }}</p>
    <p>E-mail digitado: {{ email }}</p>
  </div>
</div>
```

Neste exemplo, criamos um formulário com campos de nome e e-mail. Usamos a diretiva `v-model` para vincular os valores dos campos de entrada às variáveis `name` e `email` da instância Vue.

**2. Crie uma instância Vue:**

Agora, crie uma instância Vue que irá gerenciar os dados do formulário e definir os métodos para manipular o envio do formulário.

```javascript
new Vue({
  el: '#app',
  data: {
    name: '', // Variável para armazenar o nome
    email: '' // Variável para armazenar o e-mail
  },
  methods: {
    submitForm: function() {
      // Método chamado quando o formulário é enviado
      // Você pode acessar os valores dos campos aqui (this.name e this.email)
      // Neste exemplo, apenas exibimos os valores no console
      console.log('Nome enviado: ' + this.name);
      console.log('E-mail enviado: ' + this.email);
    }
  }
});
```

No JavaScript acima, criamos uma instância Vue associada ao elemento `#app` no HTML. Definimos as variáveis `name` e `email` no objeto `data`, que são vinculadas aos campos de entrada no formulário. Também criamos o método `submitForm`, que é chamado quando o formulário é enviado e exibe os valores no console. Você pode realizar ações de envio de formulário ou fazer solicitações HTTP dentro deste método.

Agora, quando você preencher o formulário e enviá-lo, os valores digitados nos campos de nome e e-mail serão exibidos no console. Isso é um exemplo simples de como criar um formulário Vue.js com Data Binding para capturar os dados do usuário.