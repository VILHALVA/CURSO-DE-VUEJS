# CRIANDO COMPONENTES
A criação de componentes é uma parte fundamental da estrutura de desenvolvimento em Vue.js. Os componentes permitem que você divida a interface do usuário em partes reutilizáveis, facilitando a manutenção e organização do código. Aqui está um guia passo a passo sobre como criar componentes em Vue.js:

**1. Estrutura do Projeto Vue.js:**

Certifique-se de que você está trabalhando em um projeto Vue.js. Você pode ter criado seu projeto usando o Vue CLI ou configurado manualmente. O Vue CLI gera uma estrutura de pastas que se parece com isto:

```
meu-projeto/
  |- src/
    |- components/
    |- App.vue
    |- main.js
  |- public/
  |- package.json
```

**2. Crie um novo componente:**

Vamos criar um novo componente chamado `MeuComponente.vue`. Na pasta `src/components`, crie um arquivo chamado `MeuComponente.vue` com o seguinte conteúdo:

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
      mensagem: 'Este é o meu primeiro componente Vue!'
    };
  }
};
</script>

<style scoped>
/* Estilos específicos do componente */
</style>
```

Neste exemplo, estamos criando um componente Vue chamado `MeuComponente.vue` que consiste em um template HTML, uma seção de script para a lógica do componente e uma seção de estilo.

**3. Usando o Componente:**

Para usar o componente em outro componente ou no seu aplicativo, você deve importá-lo. Por exemplo, em `App.vue`, você pode importar e usar o `MeuComponente` assim:

```vue
<template>
  <div>
    <h1>Minha Aplicação Vue</h1>
    <meu-componente></meu-componente>
  </div>
</template>

<script>
import MeuComponente from './components/MeuComponente.vue';

export default {
  components: {
    'meu-componente': MeuComponente
  }
};
</script>
```

Neste exemplo, importamos o componente `MeuComponente.vue` e o registramos no componente `App.vue`. Agora você pode usá-lo no template como `<meu-componente></meu-componente>`.

**4. Estilos de Componente:**

Os estilos em uma seção `<style>` dentro de um componente são escopados por padrão, o que significa que eles se aplicam apenas aos elementos dentro desse componente. Isso evita conflitos de estilo entre componentes.

**5. Reutilização de Componentes:**

Agora você pode usar o componente `MeuComponente` em outros lugares do seu aplicativo sempre que precisar exibir a mesma estrutura ou funcionalidade.

Criar e usar componentes é uma prática essencial em Vue.js, permitindo a criação de interfaces de usuário complexas e reutilizáveis de maneira organizada e eficiente. Certifique-se de registrar componentes quando necessário para que o Vue.js os reconheça e possa renderizá-los corretamente.