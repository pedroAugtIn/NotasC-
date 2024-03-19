Adicionar lógica de decisão ao código usando as instruções 'if', 'else' e 'else if' em C#

A linguagem de C# permite que você crie aplicativos que empregam lógicoa de tomada de decisões.
A instrução if usa uma empressão booliana colada entre parênteses. Se a expressão for verdadeira, o código após a instrução if será executada. Caso contrário o runtime do .NET ignora o código e não o executa.

A instrução if é composta por três partes:

A palavra-chave if
Uma expressão booliana entre parênteses ()
Um bloco de código definido por chaves { }

-O que é uma expressão booliana??
é qualquer código que retorna um valor booliano, true ou false. 

Outras expressões boolianas simples podem ser criadas usando operadores para comparar dois valores. Os operadores incluem:

==, o operador "igual" para testar a igualdade
>, o operador "maior que", para testar se o valor à esquerda é maior que o valor à direita
<, o operador "menor que", para testar se o valor à esquerda é menor que o valor à direita
>=, o operador "maior ou igual a"
<=, o operador "menor ou igual a"
e assim por diante

O que é um bloco de código?
Um bloco de código é uma coleção de uma ou mais linhas de código definidas por um símbolo de chave de abertura e fechamento { }. Ele representa uma unidade de código completa com uma única finalidade em seu sistema de software. Nesse caso, no runtime, todas as linhas de código no bloco de código serão executadas se a expressão booliana for verdadeira. Por outro lado, se a expressão booliana for falsa, todas as linhas de código no bloco de código serão ignoradas.

-Adicionar outra instrução if para implementar o bônus por resultado duplicado:
Os caracteres de pipe duplo || são o operador lógico OR, que basicamente afirma que "a expressão à minha esquerda OU a expressão à minha direita precisa ser verdadeira para que toda a expressão booliana seja verdadeira".

O operador >= significa "maior ou igual a".

Exemplos usados durante atividade:
if ((roll1 == roll2) || (roll2 == roll3) || (roll1 == roll3)){}
if ((roll1 == roll2) && (roll2 == roll3)){}
if (total >= 15){};
if (total < 15){};

Os caracteres de E comercial duplos && são o operador lógico AND, que basicamente afirma que "somente se duas as expressões forem verdadeira, a expressão inteira será verdadeira".

O aninhamento nos permite colocar blocos de código dentro de outros blocos de código.




