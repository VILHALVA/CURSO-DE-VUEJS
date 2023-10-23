# MÉTODOS
Em Vue.js, você pode definir métodos que são funções associadas a um componente Vue. Esses métodos podem ser chamados a partir do template do componente ou de outros métodos, permitindo que você crie a lógica do comportamento do componente. Aqui estão os passos para definir e usar métodos em um componente Vue:

**1. Definindo Métodos no Componente:**

Você pode definir métodos no bloco `methods` dentro do objeto do componente. Aqui está um exemplo simples de como definir um método:

```vue
<template>
  <div>
    <button @click="cumprimentar">Cumprimentar</button>
  </div>
</template>

<script>
export default {
  methods: {
    cumprimentar() {
      alert('Olá! Esta é uma mensagem de saudação.');
    }
  }
};
</script>
```

No exemplo acima, definimos um método chamado `cumprimentar`. Esse método é chamado quando o botão é clicado, exibindo um alerta com uma mensagem de saudação.

**2. Chamando Métodos a partir do Template:**

Você pode chamar métodos diretamente do template usando diretivas de evento, como `@click`, que disparam o método quando um evento específico ocorre. No exemplo anterior, usamos `@click="cumprimentar"` para chamar o método `cumprimentar` quando o botão é clicado.

**3. Usando Parâmetros em Métodos:**

Métodos podem aceitar parâmetros para realizar ações específicas com base nos dados fornecidos. Aqui está um exemplo de como passar parâmetros para um método:

```vue
<template>
  <div>
    <button @click="saudacao('Olá')">Dizer Olá</button>
    <button @click="saudacao('Oi')">Dizer Oi</button>
  </div>
</template>

<script>
export default {
  methods: {
    saudacao(mensagem) {
      alert(mensagem + '! Esta é uma saudação personalizada.');
    }
  }
};
</script>
```

Neste exemplo, o método `saudacao` aceita um parâmetro `mensagem` que é usado para criar saudações personalizadas com base no botão clicado.

**4. Acessando Dados do Modelo e Outros Métodos:**

Dentro de um método, você pode acessar dados do modelo e outros métodos do componente usando a palavra-chave `this`. Por exemplo:

```vue
<template>
  <div>
    <p>{{ mensagem }}</p>
    <button @click="alterarMensagem">Alterar Mensagem</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mensagem: 'Olá, Vue.js!'
    };
  },
  methods: {
    alterarMensagem() {
      this.mensagem = 'Mensagem alterada!';
    }
  }
};
</script>
```

No exemplo acima, o método `alterarMensagem` acessa a variável `mensagem` definida nos dados do modelo e a atualiza quando o botão é clicado.

Métodos são uma parte fundamental da criação de lógica em componentes Vue. Eles permitem que você responda a eventos, atualize dados e realize operações específicas dentro do seu componente, tornando sua aplicação Vue dinâmica e interativa.