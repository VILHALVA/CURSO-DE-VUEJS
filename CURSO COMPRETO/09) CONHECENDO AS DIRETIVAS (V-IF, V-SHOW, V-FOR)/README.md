# CONHECENDO AS DIRETIVAS (V-IF, V-SHOW, V-FOR)
No Vue.js, as diretivas são atributos especiais que você pode adicionar a elementos HTML para fornecer funcionalidades dinâmicas ou reativas. Algumas das diretivas mais comuns são `v-if`, `v-show` e `v-for`. Vamos dar uma olhada em cada uma delas:

**1. `v-if`**

A diretiva `v-if` é usada para renderizar um elemento somente se a expressão associada for avaliada como verdadeira. Se a expressão for falsa, o elemento não será renderizado no DOM. Aqui está um exemplo:

```vue
<template>
  <div>
    <p v-if="mostrarParagrafo">Este é um parágrafo condicional.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mostrarParagrafo: true
    };
  }
};
</script>
```

Neste exemplo, o parágrafo só será renderizado se `mostrarParagrafo` for `true`.

**2. `v-show`**

A diretiva `v-show` é semelhante ao `v-if`, mas em vez de remover o elemento do DOM quando a expressão é falsa, ela apenas o oculta definindo a propriedade `display` do elemento para "none". Aqui está um exemplo:

```vue
<template>
  <div>
    <p v-show="mostrarParagrafo">Este é um parágrafo ocultável.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mostrarParagrafo: true
    };
  }
};
</script>
```

Neste caso, o parágrafo é ocultado quando `mostrarParagrafo` é `false`, mas o elemento permanece no DOM.

**3. `v-for`**

A diretiva `v-for` é usada para renderizar uma lista de elementos com base em um array ou objeto. Você pode iterar sobre os itens da coleção e criar elementos para cada item. Aqui está um exemplo:

```vue
<template>
  <div>
    <ul>
      <li v-for="item in listaItens">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listaItens: ['Item 1', 'Item 2', 'Item 3']
    };
  }
};
</script>
```

Neste exemplo, a diretiva `v-for` cria uma lista não ordenada com os itens da matriz `listaItens`.

Além dessas diretivas, o Vue.js oferece muitas outras, como `v-bind`, `v-on`, `v-model`, `v-cloak` e muito mais. Essas diretivas são usadas para criar comportamentos reativos, manipular eventos, vincular atributos e lidar com a interação do usuário em seus componentes Vue. Elas são uma parte fundamental da construção de aplicativos reativos e dinâmicos com Vue.js.