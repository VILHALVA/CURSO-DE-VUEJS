# REMOVENDO PEDIDOS DO SISTEMA
Para remover pedidos do sistema em um aplicativo Vue.js, você precisará realizar várias etapas, incluindo a criação de uma funcionalidade de exclusão no componente de pedidos e a comunicação com a API para efetuar a remoção no banco de dados. Aqui estão as etapas:

**1. Adicione um Botão de Exclusão ao Componente de Pedidos:**

Dentro do componente `Pedidos.vue`, adicione um botão ou ícone para cada pedido na lista que permitirá aos usuários remover o pedido. Por exemplo:

```vue
<li v-for="pedido in pedidos" :key="pedido.id">
  {{ pedido.numeroPedido }} - {{ pedido.cliente }} - Status: {{ getStatus(pedido.status) }}
  <button @click="removerPedido(pedido.id)">Remover</button>
</li>
```

**2. Crie um Método para Remover Pedidos:**

No componente `Pedidos.vue`, crie um método para remover pedidos. Este método será chamado quando o usuário clicar no botão de exclusão. Aqui está um exemplo de como fazer isso:

```vue
methods: {
  // ... outros métodos

  async removerPedido(pedidoId) {
    try {
      // Faça uma solicitação DELETE para a API para remover o pedido
      await axios.delete(`/api/pedidos/${pedidoId}`); // Substitua pelo endpoint da sua API

      // Atualize a lista de pedidos após a remoção
      this.pedidos = this.pedidos.filter(pedido => pedido.id !== pedidoId);
    } catch (error) {
      console.error('Erro ao remover pedido:', error);
    }
  }
}
```

Este método envia uma solicitação DELETE para a API, informando o ID do pedido que deve ser removido. Após a remoção bem-sucedida, a lista de pedidos é atualizada localmente para refletir a remoção.

**3. Estilize o Botão de Exclusão:**

Estilize o botão de exclusão para que os usuários possam identificá-lo claramente. Você pode adicionar um ícone de exclusão ao botão para torná-lo mais visual.

**4. Teste a Exclusão de Pedidos:**

Agora você pode testar a funcionalidade de exclusão de pedidos em seu aplicativo Vue.js, certificando-se de que os pedidos sejam removidos corretamente e que a lista de pedidos seja atualizada conforme esperado.

Lembre-se de que a lógica específica de exclusão e a implementação da API podem variar de acordo com a tecnologia que você está usando para sua API e banco de dados. Certifique-se de adaptar o exemplo às necessidades específicas do seu projeto. Além disso, é importante implementar medidas de segurança na API para garantir que a exclusão de pedidos seja restrita apenas a usuários autorizados.