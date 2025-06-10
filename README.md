# Relatório Técnico - Nayara Queiroz Calenzo

## 1. Visão Geral da Solução

Este projeto consiste em uma aplicação de gerenciamento de tarefas (ToDo List), onde foi realizado o desenvolvimento das funcionalidades básicas, correção de bugs iniciais, ajustes de usabilidade e implementação de melhorias para tornar a aplicação mais estável e intuitiva.

---

## 2. Como Executar a Aplicação

Para executar a aplicação localmente, siga os passos abaixo:

```
# Clonar o repositório
git clone <URL-do-repositório>

# Entrar na pasta do projeto
cd nome-do-projeto

# Instalar as dependências
npm install

# Iniciar a aplicação
npm start
```

## 3. Correção dos Erros Iniciais (npm start):
      - Não tinha script para "start",
      - HeaderComponent estava sendo declarado mais de uma vez e faltando um "r",
      - ToDoService não estava sendo importado no new-task.component.ts,
      - Não foi criado componente para app-header,
      - fontawesome não estava instalado no projeto
## 4. Relatório de Correção de Bugs: 
   - 4.1 Ao clicar no botão “Salvar”, a tarefa está sendo adicionada duas vezes.
       - Resolução: linha de código que executa adição de tarefa duplicada, linha 25 excluída.
   - 4.2 Só está sendo possível salvar uma tarefa a primeira vez que clica no botão “Salvar”, só é possível salvar uma nova tarefa após atualizar a página (F5).
       - Resolução: Havia uma condição para executar a adicação da tarefa apenas se count fosse menor que zero, a primeira vez executava e depois ele incrementava, impossibilitando nova adição. Foi apenas retirado a condição e o count. 
   - 4.3 O texto do botão de limpar todas as tarefas não está em português.
       - Resolução: No todo.component.html estava sendo usado innerHTML para adicionar a informação com rótulo do botão em inglês. Modifiquei para inserir uma variável e chamei ela no todo.component.ts declarando tipo de dado string e o valor padrão "Limpar todas".
   - 4.4 O botão “Exibir Tarefas Concluídas” está, na verdade, ocultando as tarefas concluídas.
       - Resolução: Na função filteredTodos() o operador ternário estava com os blocos true e false invertidos, apenas troquei as posições, ocultando tarefas concluídas quando o botão mostrar concluidos for true
   - 4.5 O botão “Ocultar Tarefas Concluídas” tem o comportamento invertido, exibindo as tarefas concluídas.
       - Resolução: Como o problema 4.4 estava invertido com o 4.5 ambos foram consertados na mesma resolução. Aproveitei para mudar a variável showCompletedTasks para iniciar com "false" para que ao iniciar aplicação mostre as tarefas concluídas com o botão de ocultar tarefas concluídas, ao invés de mostrar, já que as tarefas já estavam ativas. 
   - 4.6 Ao clicar em “Limpar Tarefas Concluídas”, a ação é executada sem pedir uma confirmação ao usuário.
        - Resolução: Adicionei no método clearCompletedTasks() uma condicional para só executar o bloco de código deste método se a pessoa confirmar.
   - 4.7 O botão “Limpar Tarefas Concluídas” está removendo as tarefas não concluídas em vez das concluídas.
       - Resolução: a camada de service para tratar a limpeza das tarefas concluídas estava mantendo as tarefas concluídas mostrando os marcados como "complited" e foi resolvido mudando a filtragem para deixar as tarefas concluidas que estava como false, mantendo na tela somente as não concluídas 
   - 4.8 O botão “Editar” não está funcional. O comportamento esperado é: ao clicar, o campo “Título da Tarefa” deve ser preenchido com o texto da tarefa selecionada. Ao salvar, o item na lista deve ser atualizado e o campo de texto limpo.
   - 4.9 O botão “Editar” está desalinhado e deve ser posicionado ao lado do botão “Remover”.
   - 4.10 O botão “Remover” deve ter a cor vermelha para indicar uma ação destrutiva.
   - 4.11 A lista de tarefas não apresenta uma barra de rolagem quando o número de itens ultrapassa a altura do painel, impedindo a visualização de todas as tarefas.
   - 4.12 Salvar sem digitar um “Título da Tarefa” está adicionando um item em branco à lista.
   - 4.13 Digitar apenas espaços no campo “Título da Tarefa” e salvar também está adicionando um item em branco.
## 5. Relatório de Implementação de Melhorias: Para cada melhoria, descreva sua abordagem técnica e quais bibliotecas foram utilizadas.
## 6. Relatório de Débito Técnico: Para cada ítem da lista de bugs e melhorias que você não conseguiu resolver ou implementar, descreva quais foram as dificuldades que você enfrentou na qual fizerem com que você não tenha conseguido entregar:
  - Infelizmente só vi na segunda o email, minha caixa de email estava cheia e não estava chegando notificação. Eu trabalho como professora também e tive que dar aula hoje, o que diminuiu mais meu tempo para resolução dos problemas. Acredito que se eu tivesse visto quando recebi o email, teria conseguido entregar um resultado melhor. 
## 7. Relatório de Melhorias: Descreva quais melhorias (novas funcionalidades) você acha interessante que sejam implementadas para evoluir o sistema.
## 8. Decisões e Considerações: (Opcional) Espaço para comentar qualquer decisão de arquitetura ou desafio interessante que você encontrou.
  - Foi um desafio muito interessante, foi meu primeiro contato com Angular, o que me deixou animada pois vi que, mesmo restando pouco tempo pra fazer, decidi dar meu melhor e consegui fazer bastante coisa graças à lógica de programação que venho desenvolvendo e evoluindo. 
