-Executar operações básicas em números em C#

-Os aplicativos que você criará em C# exigirão que você execute operações em dados numéricos literais e variáveis. Os exemplos podem incluir:

Executar operações matemáticas simples, incluindo adição, subtração, multiplicação e divisão
Executar operações com várias etapas que precisam ser concluídas em uma ordem determinada
Determinar o resto após executar uma divisão
Incrementar ou decrementar um valor, e assim por diante

-Realizar adição com conversão implícita de dados:
Para somar dois números, você usará o operador de adição, que é o sinal de mais +. Sim, o mesmo símbolo de mais + que você usa para concatenação de cadeias de caracteres também é usado para adição. A reutilização de um símbolo com várias finalidades é, às vezes, chamada de "sobrecarregar o operador", e ocorre frequentemente em C#.
Neste caso, o compilador de C# entende o que você está tentando fazer. O compilador analisa o código e vê que o + (operador) está posicionado entre dois valores numéricos (operandos). Considerando os tipos de dados das variáveis (ambos são ints), ele conclui que você deseja adicionar os dois valores.

int firstNumber = 12;
int secondNumber = 7;
Console.WriteLine(firstNumber + secondNumber);

Output: 19

-Misturar tipos de dados para forçar as conversões de tipo implícitas:
O que acontece se você tenta usar o símbolo + com os valores string e int?

string firstNumber = "Bob";
int widgetSold = 7;
Console.WriteLine(firstNumber + " sold " + widgetSold + " widgets.");

Neste caso, o compilador de C# entende que você deseja usar o símbolo + para concatenar os dois operandos. Ele deduz isso porque o símbolo + está rodeado por operandos dos tipos de dados string e int. Sendo assim, ele tenta converter implicitamente a variável intwidgetsSold em um string temporariamente, para que possa concatenar o restante da cadeia de caracteres. O compilador de C# tenta ajudá-lo quando pode, mas o ideal é que você seja explícito quanto às suas intenções.

-Tentar um caso mais avançado de adição de números e concatenação de cadeias de caracteres:
string firstName = "Bob";
int widgetsSold = 7;
Console.WriteLine(firstName + " sold " + widgetsSold + 7 + " widgets.");

Em vez de adicionar a variável intwidgetsSold ao literal int7, o compilador trata tudo como uma cadeia de caracteres e concatena tudo.
Output: Bob sold 77 widgets.

-Adicionar parênteses para esclarecer sua intenção ao compilador:
string firstName = "Bob";
int widgetsSold = 7;
Console.WriteLine(firstName + " sold " + (widgetsSold + 7) + " widgets.");

Output: Bob sold 14 widgets.

O símbolo de parênteses () se torna outro operador sobrecarregado. Neste caso, os parênteses de abertura e fechamento formam o operador de ordem de operações, exatamente como você usaria em uma fórmula matemática. Você indica que quer ver o parêntese interno ser resolvido primeiro, resultando na adição dos valores int, widgetsSold e o valor 7. Após isso ser resolvido, ele converterá implicitamente o resultado em uma cadeia de caracteres para que possa ser concatenado ao restante da mensagem.

-Escrever o código para realizar a adição, subtração, multiplicação e divisão com inteiros;

int sum = 7 + 5;
int difference = 7 - 5;
int product = 7 * 5;
int quotient = 7 / 5;

Console.WriteLine("Sum: " + sum);
Console.WriteLine("Difference: " + difference);
Console.WriteLine("Product: " + product);
Console.WriteLine("Quotient: " + quotient);

Output: 
Sum: 12
Difference: 2
Product: 35
Quotient: 1

** No entanto, o quociente resultante do exemplo de divisão pode não ser o que você esperava. Os valores após a casa decimal são truncados em quotient, pois ele está definido como um int e um int não pode conter valores após a casa decimal.

-Adicionar o código para realizar uma divisão usando dados decimais literais:
Para que a divisão funcione corretamente, use um tipo de dados que dê suporte a dígitos fracionários após o ponto decimal, como decimal.

decimal decimalQuotient = 7.0m / 5;
Console.WriteLine($"Decimal quotient: {decimalQuotient}");

Output: Decimal quotient: 1.4

Para que isso funcione, o quociente (à esquerda do operador de atribuição) deve ser do tipo decimal e pelo menos um dos números que estão sendo divididos também deve ser do tipo decimal (ambos também podem ser do tipo decimal).

Aqui temos dois exemplos adicionais que funcionam tão bem quanto o anterior:
decimal decimalQuotient = 7 / 5.0m;
decimal decimalQuotient = 7.0m / 5.0m;

-Adicionar o código para converter os resultados da divisão de números inteiros:
E se você não estiver trabalhando com valores literais? Em outras palavras, e se você precisar dividir duas variáveis do tipo int, mas não quiser que o resultado seja truncado? Nesse caso, você precisa executar uma conversão de tipo de dados de int em decimal. A conversão é um tipo de conversão de dados que instrui o compilador a tratar temporariamente um valor como se ele fosse um tipo de dados diferente.

Para converter int em decimal, você adiciona o operador de conversão antes do valor. É possível usar o nome do tipo de dados entre parênteses na frente do valor para convertê-lo. Nesse caso, adicione (decimal) antes das variáveis first e second.

int first = 7;
int second = 5;
decimal quotient = (decimal)first / (decimal)second;
Console.WriteLine(quotient);

Output: 1.4

-Escrever o código para determinar o resto após a divisão de inteiros:
O operador de módulo % informa o resto da divisão de int. O que você realmente aprende com isso é se um número é divisível por outro. Isso pode ser útil durante operações de processamento longo ao percorrer em loop centenas ou milhares de registros de dados quando deseja fornecer comentários para o usuário final após cada 100 registros de dados terem sido processados.

Console.WriteLine($"Modulus of 200 / 5 : {200 % 5}");
Console.WriteLine($"Modulus of 7 / 5 : {7 % 5}");

Output:
Modulus of 200 / 5 : 0
Modulus of 7 / 5 : 2

-Ordem de operações:
Conforme você aprendeu no exercício anterior, é possível usar os símbolos () como os operadores de ordem das operações. No entanto, esta não é a única forma da ordem das operações ser determinada.

Em matemática, PEMDAS é um acrônimo que ajuda os alunos a se lembrar da ordem das operações. A ordem é:
Parêntese (o que estiver dentro do parêntese é executado primeiro)
Exponentes
Multiplicação e Divisão (da esquerda para a direita)
Adição e Subtração (da esquerda para a direita)

C# segue a mesma ordem que o acrônimo PEMDAS, exceto pelos exponentes. Embora não haja um operador de expoente em C#, é possível usar o método System.Math.Pow. O módulo "Chamar métodos da Biblioteca de Classes .NET usando C#" apresentará esse e outros métodos.

int value1 = 3 + 4 * 5;
int value2 = (3 + 4) * 5;
Console.WriteLine(value1);
Console.WriteLine(value2);

Output:
23
35

-Incrementar e decrementar:
Com frequência, você precisará incrementar e/ou decrementar valores, especialmente quando estiver escrevendo lógicas de loop ou o códigos que interagem com estruturas de dados.

O operador += adiciona e atribui o valor à direita do operador ao valor à esquerda do operador. Portanto, as linhas dois e três do seguinte snippet de código são equivalentes:

int value = 0;     // value is now 0.
value = value + 5; // value is now 5.
value += 5;        // value is now 10.

O operador ++ incrementa em uma (1) unidade o valor da variável. Portanto, as linhas dois e três do seguinte snippet de código são equivalentes:

int value = 0;     // value is now 0.
value = value + 1; // value is now 1.
value++;           // value is now 2.

Operadores como +=, -=, *=, ++ e -- são conhecidos como operadores de atribuição composta porque compõem uma operação além de atribuir o resultado à variável. O operador += é chamado especificamente de operador de atribuição de adição.
 
int value = 1;

value = value + 1;
Console.WriteLine("First increment: " + value);

value += 1;
Console.WriteLine("Second increment: " + value);

value++;
Console.WriteLine("Third increment: " + value);

value = value - 1;
Console.WriteLine("First decrement: " + value);

value -= 1;
Console.WriteLine("Second decrement: " + value);

value--;
Console.WriteLine("Third decrement: " + value);

Output:
First increment: 2
Second increment: 3
Third increment: 4
First decrement: 3
Second decrement: 2
Third decrement: 1


-Posicionar os operadores de incremento e decremento:
Os operadores de incremento e decremento têm uma característica interessante: dependendo da posição em que são usados, eles executam a operação correspondente antes ou depois de recuperarem o valor. Em outras palavras, se você usar o operador antes do valor, como em ++value, o incremento ocorrerá antes que o valor seja recuperado. Da mesma forma, value++ incrementará o valor após ele ser recuperado.

Usar o operador de incremento antes e depois do valor:
int value = 1;
value++;
Console.WriteLine("First: " + value);
Console.WriteLine($"Second: {value++}");
Console.WriteLine("Third: " + value);
Console.WriteLine("Fourth: " + (++value));

Output: 
First: 2
Second: 2
Third: 3
Fourth: 4

Observe esta linha de código: Console.WriteLine($"Second: {value++}");

Há duas etapas nesta linha:

Recuperar o valor atual da variável value e usá-lo na operação de interpolação de cadeias de caracteres.
Incrementar o valor.
A próxima linha de código confirma que o valor foi, de fato, incrementado.
Console.WriteLine("Third: " + value);

Por outro lado, considere a última linha de código:
Console.WriteLine("Fourth: " + (++value));

Aqui, a ordem das operações é alterada porque o operador ++ é colocado antes do operando value.

Incrementar o valor.
Recupere o novo valor incrementado da variável value e use-o na operação de string.
Embora não seja estritamente necessário, você adicionou parênteses em torno da expressão (++value) para melhorar a legibilidade. Ver tantos operadores + próximos uns dos outros faz com que pareça que o código poderia ser mal compreendido por outros desenvolvedores. Decisões estilísticas como essa são subjetivas. No entanto, como escreverá o código apenas uma vez, mas o lerá muitas vezes, você deve priorizar a legibilidade.


-Desafio: calcular em Celsius uma temperatura dada em Fahrenheit
int fahrenheit = 94;
decimal celsius = (fahrenheit - 32m) * (5/9m);
Console.WriteLine($"The temperature is {celsius} Celsius");

Output: 
The temperature is 34.444444444444444444444444447 Celsius.