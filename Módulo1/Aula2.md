Armazenar e recuperar dados usando valores literais e variáveis em C#

Um valor literal é um valor constante que nunca é alterado. Anteriormente, exibimos uma cadeia de caracteres literal no console de saída. Em outras palavras, você literalmente queria aquela cadeia de caracteres alfanuméricos (H, l, e, l, o e assim por diante) exibida no console de saída.

As aspas simples criam um caractere literal. Lembre-se de que usar aspas duplas cria um tipo de dados string.

Quando você usa aspas simples, o compilador C# espera apenas um caractere. Por esse motivo, se inserirmos 'Hello World!' entre aspas simples, teremos o seguinte erro:
error CS1012: Too many characters in character literal

Se quiser exibir um valor numérico inteiro (sem frações) no console de saída, você poderá usar um int literal. O termo int é abreviação de inteiro, termo que você pode reconhecer da matemática. Em C#, o nome oficial desse tipo de dados é "int", mas ele é frequentemente chamado de "inteiro". Um int literal não requer outros operadores como string ou char.

Console.WriteLine(123);

Um número de ponto flutuante é um número que contém decimais, por exemplo, 3,14159. O C# dá suporte a três tipos de dados para representar números decimais: float, double e decimal. Cada tipo dá suporte a diferentes graus de precisão.

Float Type    Precision
----------------------------
float         ~6-9 digits
double        ~15-17 digits
decimal        28-29 digits

Para criar um float literal, acrescente a letra F após o número. Nesse contexto, o F é chamado de sufixo literal. O sufixo literal informa ao compilador que você deseja trabalhar com um valor do tipo float. Você pode usar f em letras minúsculas ou F em maiúsculas como o sufixo literal para float.

Para criar um double literal, basta inserir um número decimal. O compilador usa como padrão o double literal quando um número decimal é inserido sem um sufixo literal.

Para criar um literal decimal, acrescente a letra m após o número. Nesse contexto, o m é chamado de sufixo literal. O sufixo literal informa ao compilador que você deseja trabalhar com um valor do tipo decimal. Você pode usar m em letras minúsculas ou M em maiúsculas como o sufixo literal para decimal.

Se quiser imprimir um valor representando true ou false, você pode usar um bool literal.

O termo bool é a abreviação de Boolean. Em C#, o nome oficial é "bool", mas os desenvolvedores frequentemente usam o termo "booliano" para se referir a esse tipo.

Por que enfatizar tipos de dados?
Os tipos de dados desempenham um papel fundamental em C#. De fato, a ênfase nos tipos de dados é uma das principais características que distingue o C# de outras linguagens, como Python e JavaScript.

Console.WriteLine('b');
Console.WriteLine(123);
Console.WriteLine(0.25F);
Console.WriteLine(2.625);
Console.WriteLine(12.39816m);
Console.WriteLine(true);
Console.WriteLine(false);

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

O que é uma variável?
Uma variável é um contêiner para armazenar um tipo de valor. As variáveis são importantes porque seus valores podem mudar ou variar durante a execução de um programa. As variáveis podem ser atribuídas, lidas e alteradas. Use variáveis para armazenar os valores que pretende usar em seu código.

O nome de uma variável é um rótulo amigável que o compilador atribui a um endereço de memória. Quando você quiser armazenar ou alterar valores naquele endereço de memória, ou sempre que quiser recuperar valores armazenados ali, basta usar o nome da variável criada.

Declarar uma variável
Para criar uma variável, primeiro você deve declarar o tipo de dados que ela armazenará, depois dar um nome a ela.
string firstName;

Nesse caso, você está criando uma variável do tipo string chamada firstName. De agora em diante, essa variável só pode conter valores de cadeia de caracteres.
Você pode escolher qualquer nome, desde que ele siga algumas regras da sintaxe C# para nomear variáveis.

Veja algumas considerações importantes sobre nomes de variáveis:

Os nomes de variáveis podem conter caracteres alfanuméricos e o caractere de sublinhado. Caracteres especiais como o símbolo de hash # (também conhecido como símbolo de número ou símbolo da libra) ou o símbolo do dólar $ não são permitidos.
Os nomes de variáveis precisam começar com uma letra alfabética ou um sublinhado, não um número.
Os nomes de variáveis diferenciam maiúsculas de minúsculas, o que significa que string Value; e string value; são duas variáveis diferentes.
Nomes de variáveis não podem ser uma palavra-chave do C#. Por exemplo, você não pode usar as seguintes declarações de variável: decimal decimal; ou string string;.

Aqui estão algumas convenções de codificação relacionadas a variáveis:

Os nomes de variáveis devem usar minúsculas concatenadas, que é um estilo de escrita que usa uma letra minúscula no início da primeira palavra e uma letra maiúscula no início de cada palavra subsequente. Por exemplo, string thisIsCamelCase;.
Os nomes de variáveis devem sempre começar com uma letra alfabética. Os desenvolvedores usam o sublinhado para uma finalidade especial, portanto, tente não usá-lo por enquanto.
Os nomes de variáveis devem ser descritivos e sugestivos, no contexto do aplicativo. Escolha um nome para a variável que represente o tipo de dados que ela manterá.
Os nomes de variáveis devem ser uma ou mais palavras inteiras unidas. Não use contrações ou abreviações, pois o nome da variável (e, consequentemente, a finalidade dela) pode não ficar claro para terceiros que lerem o seu código.
Nomes de variável não devem incluir o tipo de dados da variável. Você poderá ser aconselhado a usar um estilo como string strValue;. Esse conselho não é mais atual.

Aqui estão alguns exemplos de declarações de variáveis usando os tipos de dados que você aprendeu até aqui:

char userOption;

int gameScore;

decimal particlesPerMillion;

bool processedCustomer;

Para declarar uma variável, insira o tipo de dados que deseja usar seguido do nome da variável. Para atribuir um valor a uma variável, use o operador de atribuição, que é um caractere único igual a =.

Atribuir um valor inadequado a uma variável
É importante observar que a atribuição ocorre da direita para a esquerda. Em outras palavras, o compilador do C# deve primeiro entender o valor no lado direito do operador de atribuição e, em seguida, ele pode executar a atribuição à variável no lado esquerdo do operador de atribuição. Se inverter a ordem, você confundirá o compilador de C#.

Para recuperar um valor de uma variável, basta usar o nome da variável. Este exemplo atribui um valor a uma variável e, em seguida, recupera esse valor e o exibe no console.

string firstName;
firstName = "Bob";
Console.WriteLine(firstName);

Reatribuir o valor de uma variável
Você pode reutilizar e reatribuir a variável quantas vezes desejar. Este exemplo ilustra essa ideia:

string firstName;
firstName = "Bob";
Console.WriteLine(firstName);
firstName = "Liem";
Console.WriteLine(firstName);
firstName = "Isabella";
Console.WriteLine(firstName);
firstName = "Yasmin";
Console.WriteLine(firstName);

Inicializar a variável
Você deve atribuir um valor a uma variável antes de poder recuperar o valor dela. Caso contrário, você verá um erro.

Você pode declarar e definir o valor da variável em uma linha de código. Essa técnica é chamada de inicializar a variável:
string firstName = "Bob";
Console.WriteLine(firstName);

O que são variáveis locais de tipo implícito?
Uma variável local de tipo implícito é criada usando a palavra-chave var seguida de uma inicialização de variável. Por exemplo:
var message = "Hello world!";

Neste exemplo, uma variável de cadeia de caracteres foi criada usando a palavra-chave var em vez da palavra-chave string.

A palavra-chave var informa ao compilador C# que o tipo de dados está implícito pelo valor atribuído. Depois que o tipo é implícito, a variável age da mesma forma como se o próprio tipo de dados real tivesse sido usado para declará-lo. A palavra-chave var é usada para salvar em pressionamentos de tecla quando os tipos são longos ou quando o tipo é óbvio no contexto.

Como a variável message é definida imediatamente como o string valor "Hello World!", o compilador de C# entende a intenção e trata cada instância de message como uma instância do tipo string.

De fato, a variável message é definida para ser um string e para nunca poder ser alterada.

Por que usar a palavra-chave var?
A palavra-chave var foi amplamente adotado na comunidade C#. É provável que se você vir um exemplo de código em um livro ou online, verá a palavra-chave var usada em vez do nome do tipo de dados real. Portanto, é importante entender seu uso.

A palavra-chave var tem um uso importante em C#. Muitas vezes, o tipo de uma variável é óbvio com base em sua inicialização. Nesses casos, é mais simples usar a palavra-chave var. A palavra-chave var também pode ser útil ao planejar o código para um aplicativo. Ao começar a desenvolver um código para uma tarefa, talvez você não saiba imediatamente qual tipo de dados usar. Usar var pode ajudr você a desenvolver sua solução de maneira mais dinâmica.

Ao começar, é recomendável que você continue a usar o nome do tipo de dados real ao declarar variáveis até se sentir mais confortável trabalhando com código. Usar o tipo de dados ao declarar variáveis ajudará você a ser mais intencional ao escrever seu código.

