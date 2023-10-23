# MENSAGENS NAS ATUALIZAÇÕES E REMOÇÕES DE PEDIDO
Para exibir mensagens ou notificações durante as operações de atualização e remoção de pedidos, você pode aproveitar o componente de mensagens do sistema que criamos anteriormente e integrá-lo às ações de atualização e remoção de pedidos. Vou mostrar como fazer isso em um exemplo:

**1. Utilize o Componente de Mensagens do Sistema:**

Primeiro, certifique-se de que você tenha um componente de mensagens do sistema, como mencionado anteriormente. Esse componente pode ser usado para exibir notificações aos usuários após uma operação ser realizada com sucesso ou em caso de erro.

**2. Integre o Componente de Mensagens no Componente de Pedidos:**

Dentro do componente `Pedidos.vue`, importe e utilize o componente de mensagens do sistema para exibir mensagens aos usuários. Aqui está um exemplo de como você pode fazer isso:

```vue
<template>
  <div class="pedidos">
    <h2>Lista de Pedidos</h2>
    <!-- ... lista de pedidos ... -->
  </div>
</template>

<script>
import MensagensSistema from './MensagensSistema.vue'; // Importe o componente de mensagens

export default {
  components: {
    MensagensSistema // Registre o componente de mensagens
  },
  // ...
  methods: {
    // Método para exibir mensagem de sucesso
    exibirMensagemSucesso(mensagem) {
      this.$refs.mensagensSistema.adicionarMensagem(mensagem, 'success');
    },

    // Método para exibir mensagem de erro
    exibirMensagemErro(mensagem) {
      this.$refs.mensagensSistema.adicionarMensagem(mensagem, 'error');
    }
  }
};
</script>
```

Neste exemplo, estamos importando e registrando o componente `MensagensSistema` dentro do componente de `Pedidos.vue`.

**3. Use as Mensagens nas Operações de Atualização e Remoção:**

Agora, quando você realizar operações de atualização e remoção de pedidos, chame os métodos para exibir mensagens de sucesso ou erro, conforme necessário. Por exemplo:

```vue
methods: {
  // Método para remover um pedido
  async removerPedido(pedidoId) {
    try {
      // Faça uma solicitação DELETE para a API para remover o pedido
      await axios.delete(`/api/pedidos/${pedidoId}`); // Substitua pelo endpoint da sua API

      // Atualize a lista de pedidos após a remoção
      this.pedidos = this.pedidos.filter(pedido => pedido.id !== pedidoId);

      // Exiba uma mensagem de sucesso
      this.exibirMensagemSucesso('Pedido removido com sucesso.');
    } catch (error) {
      console.error('Erro ao remover pedido:', error);

      // Exiba uma mensagem de erro
      this.exibirMensagemErro('Erro ao remover pedido.');
    }
  }

  // Método para atualizar um pedido
  async atualizarPedido() {
    try {
      // Faça uma solicitação PUT ou PATCH para a API para atualizar o pedido
      await axios.put(`/api/pedidos/${this.pedido.id}`, this.pedido); // Substitua pelo endpoint da sua API

      // Exiba uma mensagem de sucesso
      this.exibirMensagemSucesso('Pedido atualizado com sucesso.');
    } catch (error) {
      console.error('Erro ao atualizar pedido:', error);

      // Exiba uma mensagem de erro
      this.exibirMensagemErro('Erro ao atualizar pedido.');
    }
  }
}
```

Dessa forma, você pode usar o componente de mensagens do sistema para informar aos usuários se uma operação de atualização ou remoção de pedido foi bem-sucedida ou se ocorreu algum erro.

**4. Estilize as Mensagens:**

Estilize as mensagens exibidas pelo componente de mensagens do sistema de acordo com o design desejado do seu aplicativo.

**5. Teste as Mensagens:**

Agora você pode testar as mensagens nas operações de atualização e remoção de pedidos em seu aplicativo Vue.js, certificando-se de que as mensagens sejam exibidas conforme o esperado.

Isso permitirá que você forneça feedback aos usuários durante as operações de atualização e remoção de pedidos, tornando a experiência do usuário mais informativa e agradável.