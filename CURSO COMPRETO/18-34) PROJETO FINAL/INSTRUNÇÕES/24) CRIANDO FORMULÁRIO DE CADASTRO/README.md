# CRIANDO FORMULÁRIO DE CADASTRO
Para criar um formulário de cadastro em um projeto Vue.js, siga estas etapas:

**1. Crie um Componente para o Formulário:**

Primeiro, crie um componente Vue para o formulário de cadastro. Você pode nomeá-lo, por exemplo, `CadastroForm.vue`. Este componente conterá o HTML e o estilo para o formulário. Aqui está um exemplo básico de um componente de formulário de cadastro:

```vue
<template>
  <div class="cadastro-form">
    <h2>Cadastro</h2>
    <form @submit="submeterFormulario">
      <div class="campo">
        <label for="nome">Nome:</label>
        <input type="text" id="nome" v-model="usuario.nome" />
      </div>
      <div class="campo">
        <label for="email">E-mail:</label>
        <input type="email" id="email" v-model="usuario.email" />
      </div>
      <div class="campo">
        <label for="senha">Senha:</label>
        <input type="password" id="senha" v-model="usuario.senha" />
      </div>
      <button type="submit">Cadastrar</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      usuario: {
        nome: '',
        email: '',
        senha: ''
      }
    };
  },
  methods: {
    submeterFormulario() {
      // Adicione a lógica para enviar os dados do formulário ao servidor ou realizar ações de cadastro.
      console.log(this.usuario);
    }
  }
};
</script>

<style scoped>
.cadastro-form {
  max-width: 400px;
  margin: 0 auto;
  padding: 2rem;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.campo {
  margin-bottom: 1rem;
}

label {
  display: block;
  font-weight: bold;
}

input {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 3px;
}

button {
  background-color: #007BFF;
  color: #fff;
  padding: 1rem 2rem;
  border: none;
  cursor: pointer;
}
</style>
```

**2. Importe o Componente de Formulário:**

Agora, importe o componente do formulário em seu layout principal ou em qualquer página onde você deseja exibir o formulário de cadastro.

**3. Estilize o Formulário:**

Estilize o componente do formulário de acordo com o design desejado do seu aplicativo. O exemplo acima contém um estilo simples, mas você pode personalizá-lo conforme necessário.

**4. Adicione Lógica de Submissão:**

No exemplo acima, a função `submeterFormulario` é chamada quando o formulário é enviado. Dentro dessa função, você pode adicionar a lógica necessária para enviar os dados do formulário ao servidor ou realizar ações de cadastro.

**5. Teste o Formulário:**

Agora você pode testar o formulário de cadastro em seu aplicativo. Certifique-se de que os campos e os estilos estejam configurados corretamente e que a lógica de submissão funcione conforme o esperado.

Este é um exemplo básico de um formulário de cadastro no Vue.js. Você pode expandir e personalizar o formulário de acordo com as necessidades do seu projeto, adicionando validação de entrada, tratamento de erros e muito mais.