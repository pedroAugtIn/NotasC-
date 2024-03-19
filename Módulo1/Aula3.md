Executar formatação de cadeia de caracteres básica em C#

Neste exercício, você aprenderá técnicas diferentes para exibir caracteres especiais e adicionar diferentes tipos de formatação à saída.

Sequências de escape de caractere
Uma sequência de caracteres de escape é uma instrução especial para que o runtime insira um caractere especial que afetará a saída da cadeia de caracteres. Em C#, a sequência de caracteres de escape começa com uma barra invertida \ seguida pelo caractere que será escapado. Por exemplo, a sequência \n adicionará uma nova linha (pula uma linha) e uma sequência \t adicionará uma guia (um longo espaço).

O seguinte código usa sequências de caracteres de escape para adicionar linhas e guias:
Console.WriteLine("Hello\nWorld!");
Console.WriteLine("Hello\tWorld!");

E se você precisar inserir uma aspa dupla em uma cadeia de caracteres literal? Se você não usar a sequência de escape de caracteres, confundirá o compilador, pois ele achará que você deseja terminar a cadeia de caracteres prematuramente. O compilador não entenderá a finalidade dos caracteres após a segunda aspa dupla.
Console.WriteLine("Hello "World"!");
O Editor .NET colocará uma linha ondulada vermelha em World. No entanto, se você tentar executar o código mesmo assim, verá a seguinte saída:
(1,27): error CS1003: Syntax error, ',' expected
(1,27): error CS0103: The name 'World' does not exist in the current context
(1,32): error CS1003: Syntax error, ',' expected

Para lidar com isso, use a sequência de escape \":
Console.WriteLine("Hello \"World\"!");

E se você precisar usar a barra invertida para outras finalidades, como exibir um caminho de arquivo? Console.WriteLine("c:\source\repos");

O C# reserva a barra invertida para sequências de escape. Portanto, se você executar o código, o compilador exibirá o seguinte erro:
(1,22): error CS1009: Unrecognized escape sequence

Para resolver o problema, use \\ para exibir uma barra invertida simples.
Console.WriteLine("c:\\source\\repos");

O escape do caractere de barra invertida produz a saída desejada:
c:\source\repos

Literal de cadeia de caracteres verbatim
Um literal de cadeia de caracteres textual manterá todo o espaço em branco e os caracteres sem a necessidade de escapar da barra invertida. Para criar uma cadeia de caracteres textual, use a diretiva @ antes da cadeia de caracteres literal.

Console.WriteLine(@"    c:\source\repos    
        (this is where your code goes)");


Caracteres de escape Unicode
Você também pode adicionar caracteres codificados em cadeias de caracteres literais usando a sequência de escape \u e, em seguida, um código de quatro caracteres representando algum caractere em Unicode (UTF-16).

// Kon'nichiwa World
Console.WriteLine("\u3053\u3093\u306B\u3061\u306F World!");

OBS: Existem várias advertências. Primeiro, alguns consoles, como o prompt de comando do Windows, não exibirão todos os caracteres Unicode. Ele substituirá esses caracteres por caracteres de ponto de interrogação. Além disso, os exemplos usados aqui são UTF-16. Alguns caracteres exigem UTF-32 e, portanto, exigem uma sequência de escape diferente. Esse é um assunto complicado, e este módulo pretende apenas mostrar o que é possível. Dependendo de sua necessidade, talvez seja necessário gastar bastante tempo aprendendo e trabalhando com caracteres Unicode em seus aplicativos.

Console.WriteLine("Generating invoices for customer \"Contoso Corp\" ...\n");
Console.WriteLine("Invoice: 1021\t\tComplete!");
Console.WriteLine("Invoice: 1022\t\tComplete!");
Console.WriteLine("\nOutput Directory:\t");
Console.Write(@"c:\invoices");

// To generate Japanese invoices:
// Nihon no seikyū-sho o seisei suru ni wa:
Console.Write("\n\n\u65e5\u672c\u306e\u8acb\u6c42\u66f8\u3092\u751f\u6210\u3059\u308b\u306b\u306f\uff1a\n\t");
// User command to run an application
Console.WriteLine(@"c:\invoices\app.exe -j");

O que é concatenação de cadeias de caracteres?
A concatenação de cadeias de caracteres consiste simplesmente na combinação de dois ou mais valores string em um novo valor string. Ao contrário da adição, o segundo valor é acrescentado ao final do primeiro valor e assim por diante.

Concatenar uma cadeia de caracteres literal e uma variável
Para concatenar duas cadeias de caracteres, use o operador de concatenação de cadeia de caracteres, que é o símbolo de adição +.

string firstName = "Bob";
string message = "Hello " + firstName;
Console.WriteLine(message);

Concatenar diversas variáveis e cadeias de caracteres literais
Você pode executar várias operações de concatenação na mesma linha de código.
string firstName = "Bob";
string greeting = "Hello";
string message = greeting + " " + firstName + "!";
Console.WriteLine(message);

O que é interpolação de cadeia de caracteres?
A interpolação de cadeia de caracteres combina vários valores em uma única cadeia de caracteres literal usando um "modelo" e uma ou mais expressões de interpolação. Uma expressão de interpolação é indicada por um símbolo de chave de abertura e fechamento { }. Você pode colocar qualquer expressão C# que retorne um valor entre chaves. A cadeia de caracteres literal se torna um modelo quando ele é prefixado pelo caractere $.

Em outras palavras, em vez de escrever a seguinte linha de código:
string message = greeting + " " + firstName + "!";

Você pode escrever esta linha de código mais concisa:
string message = $"{greeting} {firstName}!";

Usar a interpolação de cadeia de caracteres para combinar uma cadeia de caracteres literal e um valor variável
Para interpolar duas cadeias de caracteres juntas, você cria uma cadeia de caracteres literal e prefixa a cadeia de caracteres com o símbolo $. A cadeia de caracteres literal deve conter pelo menos um conjunto de chaves {}, e dentro desses caracteres você usa o nome de uma variável.

string firstName = "Bob";
string message = $"Hello {firstName}!";
Console.WriteLine(message);

int version = 11;
string updateText = "Update to Windows";
string message = $"{updateText} {version}";
Console.WriteLine(message);

int version = 11;
string updateText = "Update to Windows";
Console.WriteLine($"{updateText} {version}!");

Combinar literais textuais e interpolação de cadeia de caracteres
Suponha que você precise usar um literal textual em seu modelo. Você pode usar o símbolo @ de prefixo literal textual e o símbolo $ de interpolação de cadeia de caracteres juntos:
string projectName = "First-Project";
Console.WriteLine($@"C:\Output\{projectName}\Data");

Neste exemplo, o símbolo $ permite que você referencie a variável projectName dentro dos colchetes, enquanto o símbolo @ permite que você use o caractere \ sem escape.

string projectName = "ACME";
string russianMessage = "\u041f\u043e\u0441\u043c\u043e\u0442\u0440\u0435\u0442\u044c \u0440\u0443\u0441\u0441\u043a\u0438\u0439 \u0432\u044b\u0432\u043e\u0434";

Console.WriteLine($@"View English outuput: 
   c:\Exercise\{projectName}\data.txt");
Console.WriteLine($@"{russianMessage}:
   c:\Exercise\{projectName}\ru-RU\data.txt");

Solução alternativa:

string projectName = "ACME";
string englishLocation = $@"c:\Exercise\{projectName}\data.txt";
Console.WriteLine($"View English output:\n\t\t{englishLocation}\n");

string russianMessage = "\u041f\u043e\u0441\u043c\u043e\u0442\u0440\u0435\u0442\u044c \u0440\u0443\u0441\u0441\u043a\u0438\u0439 \u0432\u044b\u0432\u043e\u0434";
string russianLocation = $@"c:\Exercise\{projectName}\ru-RU\data.txt";
Console.WriteLine($"{russianMessage}:\n\t\t{russianLocation}\n");


