Relatório Técnico - [Nayara Queiroz Calenzo]
1. Visão Geral da Solução: Um breve resumo do que foi feito.
2. Como Executar a Aplicação: Instruções claras para clonar, instalar e rodar o projeto (npm install, npm start).
3. Correção dos Erros Iniciais (npm start):
      - Não tinha script para "start",
      - HeaderComponent estava sendo declarado mais de uma vez e faltando um "r",
      - ToDoService não estava sendo importado no new-task.component.ts,
      - Não foi criado componente para app-header,
      - fontawesome não estava instalado no projeto
4. Relatório de Correção de Bugs: 
    4.1 Ao clicar no botão “Salvar”, a tarefa está sendo adicionada duas vezes.
        Resolução: linha de código que executa adição de tarefa duplicada, linha 25 excluída. 
    4.2 Só está sendo possível salvar uma tarefa a primeira vez que clica no botão “Salvar”, só é possível salvar uma nova tarefa após atualizar a página (F5)
        Resolução: Havia uma condição para executar a adicação da tarefa apenas se count fosse menor que zero, a primeira vez executava e depois ele incrementava, impossibilitando nova adição. Foi apenas retirado a condição e o count. 
    4.3 O texto do botão de limpar todas as tarefas não está em português.
        Resolução: No todo.component.html estava sendo usado innerHTML para adicionar a informação com rótulo do botão em inglês. Modifiquei para inserir uma variável e chamei ela no todo.component.ts declarando tipo de dado string e o valor padrão "Limpar todas"
    4.4 O botão “Exibir Tarefas Concluídas” está, na verdade, ocultando as tarefas concluídas.
        Na função filteredTodos() o operador ternário estava com os blocos true e false invertidos, apenas troquei as posições, ocultando tarefas concluídas quando o botão mostrar concluidos for true
    4.5 O botão “Ocultar Tarefas Concluídas” tem o comportamento invertido, exibindo as tarefas concluídas.
        Como o problema 4.4 estava invertido com o 4.5 ambos foram consertados na mesma resolução. Aproveitei para mudar a variável showCompletedTasks para iniciar com "false" para que ao iniciar aplicação mostre as tarefas concluídas com o botão de ocultar tarefas concluídas, ao invés de mostrar, já que as tarefas já estavam ativas. 
    Ao clicar em “Limpar Tarefas Concluídas”, a ação é executada sem pedir uma confirmação ao usuário.
    O botão “Limpar Tarefas Concluídas” está removendo as tarefas não concluídas em vez das concluídas.
    O botão “Editar” não está funcional. O comportamento esperado é: ao clicar, o campo “Título da Tarefa” deve ser preenchido com o texto da tarefa selecionada. Ao salvar, o item na lista deve ser atualizado e o campo de texto limpo.
    O botão “Editar” está desalinhado e deve ser posicionado ao lado do botão “Remover”.
    O botão “Remover” deve ter a cor vermelha para indicar uma ação destrutiva.
    A lista de tarefas não apresenta uma barra de rolagem quando o número de itens ultrapassa a altura do painel, impedindo a visualização de todas as tarefas.
    Salvar sem digitar um “Título da Tarefa” está adicionando um item em branco à lista.
    Digitar apenas espaços no campo “Título da Tarefa” e salvar também está adicionando um item em branco.
5. Relatório de Implementação de Melhorias: Para cada melhoria, descreva sua abordagem técnica e quais bibliotecas foram utilizadas.
6. Relatório de Débito Técnico: Para cada ítem da lista de bugs e melhorias que você não conseguiu resolver ou implementar, descreva quais foram as dificuldades que você enfrentou na qual fizerem com que você não tenha conseguido entregar.
7. Relatório de Melhorias: Descreva quais melhorias (novas funcionalidades) você acha interessante que sejam implementadas para evoluir o sistema.
8. Decisões e Considerações: (Opcional) Espaço para comentar qualquer decisão de arquitetura ou desafio interessante que você encontrou.