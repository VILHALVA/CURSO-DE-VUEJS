# CRIANDO COMPONENTE DE MENSAGENS DO SISTEMA
Para criar um componente de mensagens do sistema em um aplicativo Vue.js, você pode seguir estas etapas:

**1. Crie um Componente para Mensagens do Sistema:**

Primeiro, crie um novo componente Vue para exibir as mensagens do sistema. Você pode nomeá-lo, por exemplo, `MensagensSistema.vue`. Este componente será responsável por exibir mensagens para o usuário, como notificações, erros ou mensagens informativas. Aqui está um exemplo básico:

```vue
<template>
  <div class="mensagens-sistema">
    <div v-for="mensagem in mensagens" :key="mensagem.id" :class="['mensagem', mensagem.tipo]">
      {{ mensagem.texto }}
      <button @click="fecharMensagem(mensagem)">Fechar</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mensagens: []
    };
  },
  methods: {
    adicionarMensagem(texto, tipo) {
      const novaMensagem = { id: Date.now(), texto, tipo };
      this.mensagens.push(novaMensagem);
    },
    fecharMensagem(mensagem) {
      const index = this.mensagens.indexOf(mensagem);
      if (index !== -1) {
        this.mensagens.splice(index, 1);
      }
    }
  }
};
</script>

<style scoped>
.mensagens-sistema {
  position: fixed;
  top: 0;
  right: 0;
  z-index: 1000;
  padding: 1rem;
}

.mensagem {
  padding: 0.5rem;
  margin: 0.5rem 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  display: flex;
  justify-content: space-between;
}

.mensagem.error {
  background-color: #f44336;
  color: #fff;
}

button {
  background-color: transparent;
  border: none;
  cursor: pointer;
  color: #007BFF;
}
</style>
```

Neste exemplo, o componente `MensagensSistema` exibe as mensagens do sistema, permitindo que você adicione mensagens (com texto e tipo) e as feche.

**2. Use o Componente de Mensagens do Sistema:**

Agora, você pode incorporar o componente `MensagensSistema` em seu layout principal ou em qualquer página onde deseja exibir mensagens do sistema. Certifique-se de importar e registrar o componente da maneira apropriada.

**3. Adicione Mensagens do Sistema:**

No restante do seu aplicativo, sempre que você desejar exibir uma mensagem do sistema, chame o método `adicionarMensagem` do componente `MensagensSistema`. Por exemplo:

```javascript
// Em qualquer componente onde você deseja exibir uma mensagem:
this.$root.$refs.mensagensSistema.adicionarMensagem('Esta é uma mensagem de sucesso.', 'success');
```

**4. Estilize o Componente:**

Personalize o componente `MensagensSistema` de acordo com o design desejado do seu aplicativo. O exemplo acima contém um estilo básico, mas você pode adaptá-lo às suas necessidades.

**5. Teste as Mensagens do Sistema:**

Agora você pode testar o componente de mensagens do sistema em seu aplicativo Vue.js. Certifique-se de que as mensagens sejam exibidas corretamente e que o usuário possa fechá-las, se necessário.

Esse é um exemplo básico de como criar um componente de mensagens do sistema em um aplicativo Vue.js. Você pode aprimorá-lo e personalizá-lo conforme necessário para atender às necessidades específicas do seu aplicativo.