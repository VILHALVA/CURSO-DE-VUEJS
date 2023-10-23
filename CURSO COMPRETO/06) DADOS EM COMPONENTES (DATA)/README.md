# DADOS EM COMPONENTES (DATA)
No Vue.js, os componentes possuem uma propriedade chamada `data`, que é uma função que retorna um objeto contendo os dados do componente. Esses dados são acessíveis no template do componente e podem ser usados para renderizar informações dinâmicas na interface do usuário. Aqui está como você define e utiliza a propriedade `data` em um componente:

**1. Definindo a propriedade `data` em um componente:**

Suponha que você tenha um componente chamado `MeuComponente` e deseja definir dados nele. Para fazer isso, você deve retornar um objeto a partir da função `data`. Por exemplo:

```vue
<template>
  <div>
    <h2>Meu Componente</h2>
    <p>{{ mensagem }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mensagem: 'Este é um componente Vue com dados!'
    };
  }
};
</script>

<style scoped>
/* Estilos específicos do componente */
</style>
```

No exemplo acima, `data` é uma função que retorna um objeto com uma única propriedade chamada `mensagem`. Esse valor será acessível no template do componente como `{{ mensagem }}`.

**2. Acessando dados no template:**

Os dados definidos na propriedade `data` do componente podem ser acessados diretamente no template do componente usando interpolação de dados (double curly braces) `{{ }}`. Por exemplo:

```vue
<template>
  <div>
    <h2>Meu Componente</h2>
    <p>{{ mensagem }}</p>
  </div>
</template>
```

No exemplo acima, `{{ mensagem }}` é usado para exibir o valor da propriedade `mensagem` definida nos dados.

**3. Modificando dados em componentes:**

Você pode modificar os dados do componente em métodos, manipuladores de eventos ou em qualquer lugar dentro do componente. Para garantir a reatividade, use a palavra-chave `this` para acessar e modificar as propriedades de `data`. Por exemplo:

```vue
<template>
  <div>
    <h2>Meu Componente</h2>
    <p>{{ mensagem }}</p>
    <button @click="alterarMensagem">Alterar Mensagem</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mensagem: 'Este é um componente Vue com dados!'
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

No exemplo acima, temos um botão que chama o método `alterarMensagem` quando é clicado, e esse método atualiza a propriedade `mensagem` no `data`.

Os dados no `data` dos componentes Vue são reativos, o que significa que qualquer alteração nos dados será automaticamente refletida na interface do usuário. Isso é uma das principais características que torna o Vue.js uma estrutura poderosa para criar interfaces de usuário dinâmicas e interativas.