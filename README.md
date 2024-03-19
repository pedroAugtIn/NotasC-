# Programa em C# que calcula as notas dos alunos com base em suas pontuações em tarefas avaliadas.

Inicialização de variáveis: O código começa declarando e inicializando algumas variáveis, como o número de tarefas avaliadas (examAssignments), as pontuações dos alunos em diferentes tarefas avaliadas (por exemplo, sophiaScores, andrewScores, etc.) e os nomes dos alunos (studentNames).

Cálculo das notas dos alunos: O código utiliza um loop foreach para iterar sobre cada aluno na lista studentNames. Para cada aluno, ele verifica a pontuação dele em tarefas avaliadas e calcula sua nota final. Isso é feito da seguinte maneira:

Primeiro, a pontuação do aluno em cada tarefa avaliada é somada. Para as tarefas avaliadas além do número especificado em examAssignments(5), a pontuação é dividida por 10 antes de ser somada, posto que referem-se a atividades extras que complementam as notas dos testes.

A nota final do aluno é calculada dividindo-se a soma das pontuações das tarefas avaliadas pelo número de tarefas avaliadas (examAssignments). O resultado é armazenado em currentStudentGrade.

Atribuição de letra de nota: Com base na nota final calculada, o programa determina a letra de nota correspondente e armazena-a em currentStudentLetterGrade. As letras de nota são atribuídas de acordo com os intervalos de notas especificados no código.

Impressão das notas dos alunos: O código imprime o nome do aluno, sua nota final e sua letra de nota correspondente na saída do console.


![image](https://github.com/pedroAugtIn/NotasC-/assets/158518938/69849a99-0aed-47d9-91cb-718367e19bc2)
