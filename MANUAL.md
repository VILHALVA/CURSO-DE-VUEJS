# MANUAL
## TUTORIAL:
Para criar um projeto Vue.js, você pode usar o Vue CLI (Interface de Linha de Comando). O Vue CLI é uma ferramenta oficial para criar, expandir e gerenciar projetos Vue.js. Vou guiá-lo através dos passos básicos para criar um novo projeto Vue.js usando o Vue CLI:

### Passo 1: Instalação do Vue CLI
Se você ainda não tem o Vue CLI instalado, pode instalá-lo globalmente usando npm (Node Package Manager). Abra o terminal ou prompt de comando e execute o seguinte comando:

```bash
npm install -g @vue/cli
```

### Passo 2: Criando um Novo Projeto Vue.js
Depois de instalar o Vue CLI, você pode criar um novo projeto Vue.js. Navegue até o diretório onde deseja criar o projeto e execute o seguinte comando:

```bash
vue create nome-do-seu-projeto
```

Substitua `nome-do-seu-projeto` pelo nome desejado para o seu projeto.

### Passo 3: Escolha de Opções
Depois de executar o comando, você será solicitado a escolher algumas opções para configurar o projeto:

- Selecione `default (babel, eslint)` para usar Babel e ESLint.
- Escolha as configurações de ESLint que você prefere (ou aceite as configurações padrão).
- Aguarde enquanto o Vue CLI cria o projeto e instala as dependências necessárias.

### Passo 4: Navegação para o Diretório do Projeto
Após a criação do projeto, navegue para o diretório do projeto usando o seguinte comando:

```bash
cd nome-do-seu-projeto
```

### Passo 5: Executando o Servidor de Desenvolvimento
Por fim, execute o servidor de desenvolvimento para visualizar o seu projeto Vue.js. Use o seguinte comando:

```bash
npm run serve
```

Isso iniciará o servidor de desenvolvimento e você poderá acessar o projeto no navegador digitando `http://localhost:8080` na barra de endereços.

### Passo 6: Explorando o Projeto
Agora você pode começar a explorar e editar o projeto Vue.js. Os arquivos principais estão localizados na pasta `src`. O arquivo principal é `App.vue`, que contém o componente raiz da aplicação Vue.js.

Você também pode adicionar novos componentes, rotas, estilos e outras funcionalidades conforme necessário para o seu projeto.

Este é apenas um guia básico para criar um projeto Vue.js. Conforme você ganha mais experiência com o Vue.js e o Vue CLI, você aprenderá mais sobre suas configurações e recursos avançados. Certifique-se de consultar a documentação oficial do Vue CLI para obter informações detalhadas sobre como trabalhar com projetos Vue.js.

## EXEMPLO DE CÓDIGO:
Este exemplo criará um componente de contador que permite ao usuário aumentar e diminuir um contador.

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vue.js Counter Example</title>
    <!-- Incluindo a biblioteca Vue.js -->
    <script src="https://cdn.jsdelivr.net/npm/vue@2"></script>
</head>
<body>
    <div id="app">
        <!-- Componente do contador -->
        <counter></counter>
    </div>

    <!-- Nosso componente Vue.js -->
    <script src="counter.js"></script>
</body>
</html>
```

```javascript
// counter.js
// Definindo um novo componente Vue.js chamado 'counter'
Vue.component('counter', {
    // Template HTML do componente
    template: `
        <div>
            <h2>Contador: {{ count }}</h2>
            <button @click="increment">Incrementar</button>
            <button @click="decrement">Decrementar</button>
        </div>
    `,
    // Dados do componente (estado)
    data() {
        return {
            count: 0
        };
    },
    // Métodos do componente
    methods: {
        increment() {
            this.count++;
        },
        decrement() {
            this.count--;
        }
    }
});

// Inicializando o aplicativo Vue.js
new Vue({
    el: '#app' // Monta o aplicativo Vue.js no elemento com o ID 'app'
});
```

### Explicação:
- **index.html:** Este é o arquivo HTML principal. Ele inclui a biblioteca Vue.js através de um CDN (Content Delivery Network) e define um elemento `<div>` com o ID "app" onde o aplicativo Vue.js será montado. Ele também inclui o script `counter.js` que contém a definição do componente Vue.js.

- **counter.js:** Este arquivo contém a definição do componente Vue.js. Usamos `Vue.component()` para criar um novo componente chamado "counter". O componente tem um template HTML que define a estrutura do componente, incluindo um título, um contador e dois botões para incrementar e decrementar o contador. O componente também tem um objeto `data` que define o estado do componente, neste caso, apenas um valor `count` inicializado como 0. Também temos métodos `increment()` e `decrement()` para atualizar o valor do contador quando os botões são clicados. No final, inicializamos o aplicativo Vue.js com `new Vue()` e montamos o aplicativo no elemento com o ID "app".

Este é um exemplo simples de um componente Vue.js que demonstra como criar e usar componentes, gerenciar estado e lidar com eventos. Com o Vue.js, você pode criar aplicativos web complexos e interativos de forma eficiente e elegante.

## DIRETÓRIO:
Ao criar um novo projeto Vue.js, a estrutura de diretórios padrão geralmente se parece com isto:
```markdown
├── public/              # Arquivos públicos
│   ├── index.html       # Arquivo HTML principal
│   └── ...
├── src/                 # Código-fonte da aplicação
│   ├── assets/          # Arquivos de assets como imagens, fontes, etc.
│   ├── components/      # Componentes Vue reutilizáveis
│   ├── views/           # Componentes de visualização (rotas ou páginas)
│   ├── App.vue          # Componente raiz da aplicação
│   └── main.js          # Arquivo de entrada JavaScript da aplicação
├── .gitignore           # Arquivo de configuração do git para ignorar arquivos/diretórios
├── babel.config.js      # Configuração do Babel
├── package.json         # Arquivo de configuração do npm com dependências e scripts
└── README.md            # Documentação do projeto
```

Aqui está uma explicação mais detalhada da estrutura de diretórios:

- **public/**: Este diretório contém os arquivos que serão diretamente servidos pelo servidor. O arquivo `index.html` é o arquivo HTML principal da aplicação, onde a montagem da aplicação Vue.js ocorre.

- **src/**: Este é o diretório principal do código-fonte da aplicação Vue.js. Ele contém os seguintes subdiretórios:
  - **assets/**: Este diretório é usado para armazenar arquivos de assets estáticos como imagens, fontes, etc.
  - **components/**: Este diretório contém componentes Vue.js reutilizáveis que podem ser usados em toda a aplicação.
  - **views/**: Este diretório geralmente contém os componentes de visualização da aplicação, que correspondem a diferentes rotas ou páginas.
  - **App.vue**: Este é o componente raiz da aplicação Vue.js. Ele encapsula toda a aplicação e pode conter componentes globais e estilos.
  - **main.js**: Este é o arquivo de entrada JavaScript da aplicação, onde a instância Vue.js é criada e montada na página.

- **.gitignore**: Este arquivo especifica quais arquivos e diretórios devem ser ignorados pelo Git durante o controle de versão.

- **babel.config.js**: Este arquivo contém a configuração do Babel, que é usado para transpilar o código JavaScript para uma versão compatível com diferentes navegadores.

- **package.json**: Este arquivo contém as dependências do projeto e scripts de gerenciamento de tarefas definidos para o npm.

- **README.md**: Este é o arquivo de documentação do projeto, geralmente contendo informações sobre como configurar, instalar e usar a aplicação.

Esta estrutura de diretórios é comum em projetos Vue.js, mas pode variar dependendo das necessidades específicas do projeto e das preferências do desenvolvedor.
