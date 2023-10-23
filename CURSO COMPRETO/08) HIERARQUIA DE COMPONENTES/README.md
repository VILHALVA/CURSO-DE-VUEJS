# HIERARQUIA DE COMPONENTES
No Vue.js, você pode criar uma hierarquia de componentes aninhando componentes uns dentro dos outros. Isso permite que você divida sua interface de usuário em partes menores e mais gerenciáveis, criando componentes reutilizáveis e organizando seu código de maneira eficiente. Aqui está como você pode criar uma hierarquia de componentes:

**1. Criando Componentes Aninhados:**

Para criar uma hierarquia de componentes, você pode definir componentes filhos dentro de componentes pais. Por exemplo, crie um componente pai chamado `PaiComponente` e um componente filho chamado `FilhoComponente`:

```vue
// PaiComponente.vue
<template>
  <div>
    <h2>Componente Pai</h2>
    <filho-componente></filho-componente>
  </div>
</template>

<script>
import FilhoComponente from './FilhoComponente.vue';

export default {
  components: {
    'filho-componente': FilhoComponente
  }
};
</script>
```

```vue
// FilhoComponente.vue
<template>
  <div>
    <h3>Componente Filho</h3>
  </div>
</template>
```

No exemplo acima, o componente `PaiComponente` inclui o componente `FilhoComponente` no seu template usando `<filho-componente></filho-componente>`. O componente pai também importa o componente filho e o registra usando `components`.

**2. Comunicação entre Componentes Aninhados:**

Os componentes aninhados podem se comunicar uns com os outros passando dados e eventos. Para passar dados de um componente pai para um filho, você pode usar as `props`. Para emitir eventos do filho para o pai, você pode usar `$emit`. Aqui está um exemplo de comunicação de pai para filho usando props:

```vue
// PaiComponente.vue
<template>
  <div>
    <h2>Componente Pai</h2>
    <filho-componente :mensagem="mensagemDoPai"></filho-componente>
  </div>
</template>

<script>
import FilhoComponente from './FilhoComponente.vue';

export default {
  data() {
    return {
      mensagemDoPai: 'Olá do Pai!'
    };
  },
  components: {
    'filho-componente': FilhoComponente
  }
};
</script>
```

```vue
// FilhoComponente.vue
<template>
  <div>
    <h3>Componente Filho</h3>
    <p>{{ mensagem }}</p>
  </div>
</template>

<script>
export default {
  props: {
    mensagem: String
  }
};
</script>
```

No exemplo acima, o componente `PaiComponente` passa a mensagem `"Olá do Pai!"` para o componente `FilhoComponente` usando uma prop chamada `mensagem`. O componente filho exibe essa mensagem em seu template.

**3. Comunicação de Filho para Pai:**

Para emitir eventos do filho para o pai, você pode usar o método `$emit`. Aqui está um exemplo simples:

```vue
// FilhoComponente.vue
<template>
  <div>
    <h3>Componente Filho</h3>
    <button @click="enviarEvento">Enviar Evento para o Pai</button>
  </div>
</template>

<script>
export default {
  methods: {
    enviarEvento() {
      this.$emit('evento-filho');
    }
  }
};
</script>
```

```vue
// PaiComponente.vue
<template>
  <div>
    <h2>Componente Pai</h2>
    <filho-componente @evento-filho="lidarComEventoFilho"></filho-componente>
  </div>
</template>

<script>
import FilhoComponente from './FilhoComponente.vue';

export default {
  methods: {
    lidarComEventoFilho() {
      console.log('Evento do Filho recebido no Pai');
    }
  },
  components: {
    'filho-componente': FilhoComponente
  }
};
</script>
```

Neste exemplo, o componente `FilhoComponente` emite um evento chamado `evento-filho` quando o botão é clicado, e o componente `PaiComponente` lida com esse evento usando `@evento-filho="lidarComEventoFilho"`.

Isso demonstra como você pode criar uma hierarquia de componentes no Vue.js e permitir que eles se comuniquem uns com os outros, tornando seu código mais organizado e reutilizável.