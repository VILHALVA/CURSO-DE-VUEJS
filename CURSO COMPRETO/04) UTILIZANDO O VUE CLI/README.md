# UTILIZANDO O VUE CLI
O Vue CLI (Command Line Interface) é uma ferramenta oficial para criar, configurar e gerenciar projetos Vue.js. Ele simplifica o processo de configuração de projetos Vue.js, fornece estruturas e opções predefinidas e ajuda a automatizar tarefas de desenvolvimento. Para começar a usar o Vue CLI, siga estas etapas:

**1. Instale o Vue CLI globalmente (se ainda não estiver instalado):**

Você pode instalar o Vue CLI globalmente em seu sistema usando o npm (Node Package Manager) executando o seguinte comando:

```bash
npm install -g @vue/cli
```

**2. Crie um novo projeto Vue com o Vue CLI:**

Depois de instalar o Vue CLI, você pode criar um novo projeto Vue com um conjunto predefinido de configurações executando o seguinte comando:

```bash
vue create nome-do-seu-projeto
```

Substitua `nome-do-seu-projeto` pelo nome que você deseja dar ao seu projeto. O Vue CLI fará algumas perguntas para você escolher as configurações do projeto, como a versão do Vue.js a ser usada e a configuração inicial. Você pode escolher a configuração padrão ou configurá-la de acordo com suas necessidades.

**3. Execute seu projeto Vue:**

Após a criação do projeto, você pode navegar até o diretório do projeto e iniciar um servidor de desenvolvimento com o seguinte comando:

```bash
cd nome-do-seu-projeto
npm run serve
```

Isso iniciará um servidor de desenvolvimento local e fornecerá um URL, geralmente `http://localhost:8080/`, onde você pode acessar seu projeto em execução. O Vue CLI também oferece recursos de recarga automática, o que significa que as alterações no código serão refletidas automaticamente no navegador.

**4. Desenvolva seu projeto Vue:**

Agora você está pronto para desenvolver seu projeto Vue. O código-fonte estará na pasta do projeto, e você pode editar os arquivos Vue, componentes, estilos e outros recursos conforme necessário. Você também pode adicionar novos componentes, gerenciar dependências e executar comandos para criar, compilar e implantar seu aplicativo.

**5. Compilar e construir para produção:**

Quando estiver pronto para implantar seu aplicativo em produção, você pode usar o Vue CLI para compilar e construir a versão final do aplicativo. Para isso, execute o seguinte comando:

```bash
npm run build
```

Isso criará uma pasta `dist` no diretório do seu projeto, contendo os arquivos otimizados para produção que podem ser implantados em um servidor web.

O Vue CLI é uma ferramenta poderosa que simplifica o desenvolvimento de aplicativos Vue.js e ajuda a manter as melhores práticas. Você pode personalizar ainda mais a configuração do projeto, adicionar plugins e estender a funcionalidade do Vue CLI conforme necessário para atender aos requisitos do seu projeto.