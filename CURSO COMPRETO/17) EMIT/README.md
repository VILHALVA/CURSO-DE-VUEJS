# EMIT
A função `emit` não é nativa do Vue.js, mas geralmente é usada para criar eventos personalizados e emitir esses eventos a partir de um componente filho para seu componente pai. Isso é útil quando você deseja comunicar ações ou eventos específicos do componente filho ao componente pai.

Aqui está como usar o `emit` para criar e emitir eventos personalizados:

**No componente filho:**

1. No componente filho, você pode usar o método `this.$emit(evento, dados)` para emitir um evento personalizado. O `evento` é uma string que define o nome do evento e `dados` é opcional, representando os dados que você deseja passar junto com o evento.

```vue
<template>
  <button @click="enviarEvento">Emitir Evento</button>
</template>

<script>
export default {
  methods: {
    enviarEvento() {
      this.$emit('evento-personalizado', { mensagem: 'Olá do filho!' });
    }
  }
};
</script>
```

Neste exemplo, o componente filho emite um evento personalizado chamado 'evento-personalizado' com um objeto de dados que contém a mensagem 'Olá do filho!'.

**No componente pai:**

2. No componente pai, você pode escutar e responder a eventos personalizados usando a diretiva `v-on` ou seu atalho `@`. O nome do evento a ser escutado deve corresponder ao nome do evento emitido pelo componente filho.

```vue
<template>
  <div>
    <meu-componente @evento-personalizado="lidarComEvento"></meu-componente>
    <p>{{ mensagemRecebida }}</p>
  </div>
</template>

<script>
import MeuComponente from './MeuComponente.vue';

export default {
  data() {
    return {
      mensagemRecebida: ''
    },
    methods: {
      lidarComEvento(dados) {
        this.mensagemRecebida = dados.mensagem;
      }
    },
    components: {
      'meu-componente': MeuComponente
    }
  }
};
</script>
```

Neste exemplo, o componente pai escuta o evento 'evento-personalizado' emitido pelo componente filho e chama a função `lidarComEvento` para lidar com os dados passados pelo evento. A mensagem recebida do componente filho é então exibida no template do componente pai.

O uso do `emit` e eventos personalizados é uma maneira poderosa de permitir que componentes filhos comuniquem informações ou ações específicas com seus componentes pais, tornando seu aplicativo mais interativo e flexível.