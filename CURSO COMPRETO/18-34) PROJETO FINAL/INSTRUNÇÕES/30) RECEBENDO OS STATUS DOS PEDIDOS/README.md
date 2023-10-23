# RECEBENDO OS STATUS DOS PEDIDOS
Para receber os status dos pedidos em um aplicativo Vue.js, você pode estender a funcionalidade do componente de pedidos que já criamos na resposta anterior. Os status dos pedidos podem ser armazenados no banco de dados e recuperados juntamente com os dados dos pedidos. Aqui estão os passos para fazê-lo:

**1. Modificando o Banco de Dados:**

Primeiro, você precisará ajustar a estrutura do seu banco de dados para incluir informações de status relacionadas aos pedidos. Isso pode ser feito adicionando uma coluna de "status" à tabela de pedidos, que armazena o status de cada pedido.

**2. Modificando a API:**

Em seguida, você deve atualizar a sua API para incluir a lógica de recuperação dos status dos pedidos. Certifique-se de que a API forneça um endpoint que permita buscar tanto os dados dos pedidos quanto os status correspondentes.

**3. Atualizando o Componente de Pedidos:**

Agora, atualize o componente `Pedidos.vue` para exibir os status dos pedidos junto com os dados dos pedidos. Você pode fazer isso de várias maneiras, mas uma abordagem comum é usar um objeto de mapeamento para associar os IDs dos status aos nomes dos status. 

Aqui está um exemplo de como você pode fazer isso:

```vue
<template>
  <div class="pedidos">
    <h2>Lista de Pedidos</h2>
    <ul>
      <li v-for="pedido in pedidos" :key="pedido.id">
        {{ pedido.numeroPedido }} - {{ pedido.cliente }} - Status: {{ getStatus(pedido.status) }}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      pedidos: []
    };
  },
  mounted() {
    // Recupere os dados dos pedidos e dos status da API
    axios.get('/api/pedidos') // Substitua pelo endpoint da sua API
      .then(response => {
        this.pedidos = response.data;
      })
      .catch(error => {
        console.error('Erro ao recuperar dados dos pedidos:', error);
      });
  },
  methods: {
    getStatus(statusId) {
      const statusMap = {
        1: 'Aguardando Pagamento',
        2: 'Em Processamento',
        3: 'Enviado',
        4: 'Entregue'
        // Adicione outros status conforme necessário
      };
      return statusMap[statusId] || 'Desconhecido';
    }
  }
};
</script>
```

Neste exemplo, o componente `Pedidos.vue` faz uma solicitação GET à API para recuperar os dados dos pedidos, que incluem o ID do status. O método `getStatus` mapeia o ID do status para um nome legível, que é exibido na lista de pedidos.

**4. Estilize o Componente de Pedidos:**

Estilize o componente `Pedidos.vue` de acordo com o design desejado da lista de pedidos, incluindo a exibição dos status.

**5. Teste os Pedidos com os Status:**

Agora você pode testar a tela de pedidos em seu aplicativo Vue.js, certificando-se de que os dados dos pedidos e seus status sejam carregados corretamente e exibidos conforme o esperado.

Lembre-se de que a estrutura do seu banco de dados, a lógica da API e o design do seu aplicativo podem variar de acordo com as necessidades específicas do seu projeto. A resposta acima fornece um exemplo básico de como você pode recuperar e exibir os status dos pedidos no seu aplicativo Vue.js.