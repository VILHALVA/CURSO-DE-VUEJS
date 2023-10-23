# EVENTOS (@SUBMIT E @CLICK)
No Vue.js, você pode lidar com eventos, como clique de botão e envio de formulário, usando as diretivas `@click` e `@submit`. Aqui estão exemplos de como usar essas diretivas:

**1. Lidando com o evento de clique (@click):**

A diretiva `@click` permite que você responda a eventos de clique em elementos HTML, como botões. Aqui está um exemplo simples:

```vue
<template>
  <div>
    <button @click="exibirMensagem">Clique em Mim</button>
  </div>
</template>

<script>
export default {
  methods: {
    exibirMensagem() {
      alert('Botão clicado!');
    }
  }
};
</script>
```

Neste exemplo, a função `exibirMensagem` é chamada quando o botão é clicado, exibindo um alerta com a mensagem "Botão clicado!".

**2. Lidando com o evento de envio de formulário (@submit):**

A diretiva `@submit` permite que você responda a eventos de envio de formulário. Você geralmente a usará em elementos `<form>` para executar ações quando o usuário envia o formulário. Aqui está um exemplo:

```vue
<template>
  <div>
    <form @submit="enviarFormulario">
      <input type="text" v-model="mensagem" placeholder="Digite uma mensagem">
      <button type="submit">Enviar</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mensagem: ''
    };
  },
  methods: {
    enviarFormulario(event) {
      event.preventDefault(); // Impede o envio padrão do formulário
      alert('Mensagem enviada: ' + this.mensagem);
      this.mensagem = ''; // Limpa o campo de entrada
    }
  }
};
</script>
```

Neste exemplo, a função `enviarFormulario` é chamada quando o formulário é enviado. Ela impede o envio padrão do formulário usando `event.preventDefault()`, exibe um alerta com a mensagem digitada e limpa o campo de entrada.

Essas são as diretrizes `@click` e `@submit` no Vue.js, que permitem que você responda a eventos de clique de botão e envio de formulário em seus componentes Vue. Você pode personalizar a lógica do evento conforme necessário para atender aos requisitos do seu aplicativo.