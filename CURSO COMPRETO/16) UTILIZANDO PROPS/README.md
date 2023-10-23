# UTILIZANDO PROPS
No Vue.js, você pode usar `props` para passar dados de um componente pai para um componente filho. Props são uma forma de tornar os componentes reutilizáveis e personalizáveis, permitindo que você compartilhe informações específicas com os componentes filhos. Aqui está como você pode utilizar `props`:

**1. Definindo Props no Componente Filho:**

No componente filho, você precisa definir as props que deseja receber. Isso é feito na seção `props` do componente filho. Por exemplo:

```vue
<template>
  <div>
    <p>{{ mensagem }}</p>
  </div>
</template>

<script>
export default {
  props: {
    mensagem: String // Define uma prop chamada "mensagem" do tipo String
  }
};
</script>
```

Neste exemplo, o componente filho define uma prop chamada "mensagem" que espera receber uma string.

**2. Passando Props do Componente Pai para o Filho:**

No componente pai, você pode passar as props para o componente filho como atributos. Aqui está um exemplo:

```vue
<template>
  <div>
    <meu-componente :mensagem="mensagemDoPai"></meu-componente>
  </div>
</template>

<script>
import MeuComponente from './MeuComponente.vue';

export default {
  data() {
    return {
      mensagemDoPai: 'Olá do Pai!'
    };
  },
  components: {
    'meu-componente': MeuComponente
  }
};
</script>
```

No exemplo acima, o componente pai usa `:mensagem="mensagemDoPai"` para passar a prop `mensagem` com o valor da variável `mensagemDoPai` para o componente filho.

**3. Acessando Props no Componente Filho:**

No componente filho, você pode acessar as props usando `this`. Por exemplo:

```vue
<template>
  <div>
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

No exemplo acima, o valor da prop `mensagem` passado pelo componente pai é exibido no template do componente filho.

**4. Tipagem de Props:**

Você pode definir o tipo esperado das props para ajudar na validação e na documentação do componente. No exemplo acima, a prop `mensagem` é definida como do tipo `String`. Se o tipo da prop não corresponder ao esperado, o Vue.js emitirá um aviso no console.

Usar props é uma maneira eficaz de passar dados de um componente pai para um componente filho e torná-los altamente reutilizáveis. Você pode passar qualquer tipo de dado como prop, incluindo objetos e funções, tornando seus componentes flexíveis e personalizáveis.