# CSS SCOPED E CSS GLOBAL
No Vue.js, você pode aplicar estilos a componentes de duas maneiras principais: com CSS global e com CSS scoped. Cada abordagem tem suas próprias características e é útil em diferentes situações.

**CSS Global:**

Quando você aplica estilos globalmente em um aplicativo Vue.js, os estilos afetam todos os componentes em seu aplicativo. Isso é útil para estilos que são comuns a toda a aplicação, como estilos para o corpo da página, barras de navegação ou botões globais. Aqui está como você pode definir estilos globais:

1. Crie um arquivo CSS ou SCSS separado com seus estilos globais. Por exemplo, `styles.css`.

2. Importe esse arquivo em seu ponto de entrada principal, geralmente `main.js`:

```javascript
import Vue from 'vue';
import App from './App.vue';
import './styles.css'; // Importe seu arquivo CSS global aqui

new Vue({
  render: h => h(App),
}).$mount('#app');
```

Dessa forma, os estilos no arquivo `styles.css` serão aplicados a todos os componentes em seu aplicativo.

**CSS Scoped:**

Ao usar estilos scoped, você limita os estilos a um componente específico, impedindo que esses estilos afetem outros componentes. Cada componente Vue.js pode ter seu próprio estilo, garantindo encapsulamento e evitando conflitos de estilo entre componentes. Aqui está como você pode aplicar estilos scoped:

1. Em um componente Vue, você pode definir a seção `<style scoped>` para criar estilos específicos desse componente:

```vue
<template>
  <div>
    <p>Este é um componente Vue com estilos scoped.</p>
  </div>
</template>

<script>
export default {
  // ... configuração do componente
};
</script>

<style scoped>
/* Estilos específicos do componente */
p {
  color: red;
}
</style>
```

Os estilos dentro da seção `<style scoped>` serão aplicados apenas a este componente e não afetarão outros componentes.

**Nota Importante:**

É importante notar que os estilos scoped funcionam por meio da geração automática de atributos `data-v-xxxxxx` em cada elemento do componente para garantir a aplicação correta dos estilos. Isso garante que os estilos sejam restritos ao escopo do componente.

A escolha entre estilos globais e estilos scoped depende do que você está tentando alcançar. Use estilos globais para estilizar elementos compartilhados em todo o aplicativo e estilos scoped para componentes específicos, mantendo uma clara separação de preocupações e evitando conflitos de estilo. Ambas as abordagens são poderosas e podem ser usadas juntas em um aplicativo Vue.js, dependendo dos requisitos de design e organização do projeto.