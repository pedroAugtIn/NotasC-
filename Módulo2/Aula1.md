Inicialmente instalar o visual studio code;
Depois Instalar o .Net;

No prompt de comando Terminal, para criar o novo aplicativo de console na pasta especificada, insira o comando a seguir:
dotnet new console -o ./CsharpProjects/TestProject

Você deve ver a pasta TestProject e dois arquivos: o arquivo de programa do C#, denominado Program.cs, e o arquivo de projeto do C#, denominado TestProject.csproj. O comando da CLI usa o nome da pasta ao criar o arquivo de projeto (TestProject.csproj). O arquivo Program.cs é o arquivo que contém o código em C#.

Na exibição “GERENCIADOR” do Visual Studio Code, clique com o botão direito do mouse na pasta do TestProject e selecione Abrir no Terminal Integrado.

O prompt de comando no painel “Terminal Integrado” mostra o local de pasta em que o comando será executado. Antes de executar um comando build ou run, verifique se o Terminal está aberto na pasta do projeto.

Para realizar uma compilação do aplicativo, insira o seguinte comando no prompt de comando do Terminal: 
dotnet build

O comando dotnet build compila o projeto e suas dependências em um conjunto de binários. Os binários incluem o código do projeto em arquivos de linguagem intermediária (IL) com uma extensão .dll. Dependendo do tipo de projeto e das configurações, outros arquivos também podem ser incluídos. Se estiver curioso, confira o arquivo TestProject.dll no painel “GERENCIADOR” em um local de pasta semelhante ao seguinte:

C:\Users\someuser\Desktop\CsharpProjects\TestProject\bin\Debug\net7.0\

Para executar o aplicativo, digite o seguinte comando no prompt de comando do Terminal:
dotnet run

O comando dotnet run executa o código-fonte sem nenhum comando explícito de compilação ou inicialização. Ele fornece uma opção conveniente para executar o aplicativo no código-fonte com um único comando. Ele é útil para o desenvolvimento iterativo rápido a partir da linha de comando. O comando depende do comando dotnet build para compilar o código.


Pense em uma classe como um contêiner para métodos ou como as seções da biblioteca pública. Os desenvolvedores normalmente mantêm os métodos relacionados juntos em uma única classe. Como você viu no exemplo anterior, todos os métodos que podem enviar ou receber informações de uma janela de console são coletados na classe System.Console da biblioteca de classes do .NET.

-Como chamar métodos na Biblioteca de Classes do .NET
Com base em sua experiência anterior com o método Console.WriteLine(), você já deve conhecer os conceitos básicos:

Comece digitando o nome da classe. Neste caso, o nome da classe é Console.
Adicione o operador de acesso de membro, o símbolo ..
Adicione o nome do método. Neste caso, o nome do método é WriteLine.
Adicione o operador de chamada do método, que é um conjunto de parênteses ().
Finalmente, especifique os argumentos que serão transmitidos ao método, se houver algum, entre os parênteses do operador de invocação de método. Aqui, você especifica o texto que deseja que o método Console.WriteLine() escreva no console (por exemplo, "Hello World!").



--- No prompt de comando Terminal, para criar o novo aplicativo de console na pasta especificada, digite dotnet new console -o ./CsharpProjects/TestProject e pressione Enter.

No painel EXPLORER, para abrir o Terminal no local da pasta TestProject, clique com o botão direito do mouse em TestProject e selecione Abrir no Terminal Integrado.
No prompt de comando do Terminal, para executar o código, digite dotnet run e pressione Enter.


-Criar uma instância de uma classe:
Uma instância de uma classe é chamada de um objeto. Para criar uma instância de uma classe, use o operador new. Considere a seguinte linha de código que cria uma instância da classe Random para criar um objeto chamado dice:
Random dice = new Random();

O operador new faz várias coisas importantes:

Primeiro, ele solicita um endereço na memória do computador grande o suficiente para armazenar um novo objeto com base na classe Random.
Ele cria o objeto e o armazena no endereço de memória.
Ele retorna o endereço de memória para que ele possa ser salvo na variável dice.
Desse ponto em diante, quando a variável dice é referenciada, o Tempo de Execução do .NET executa uma pesquisa nos bastidores para dar a ilusão de que você está trabalhando diretamente com o próprio objeto.

A versão mais recente do Runtime do .NET permite que você crie uma instância de um objeto sem ter que repetir o nome do tipo (invocação de construtor com tipo de destino). Por exemplo, o código a seguir criará uma nova instância da classe Random:
Random dice = new();


Random dice = new Random();
int roll = dice.Next(1, 7);
Console.WriteLine(roll);

A primeira linha de código cria uma instância da classe Random chamada dice. A segunda linha de código usa o método dice.Next(1, 7) para atribuir um valor aleatório a um número inteiro chamado roll. Observe que a instrução chamada fornece dois argumentos separados por um símbolo ,. O método Next() inclui uma assinatura de método que aceita dois parâmetros de entrada do tipo int. Esses parâmetros são usados para configurar os marcos de delimitação inferior e superior do número aleatório que é retornado. A linha de código final usa o método Console.WriteLine() para imprimir o valor de roll no console.


Random dice = new Random();
int roll1 = dice.Next();
int roll2 = dice.Next(101);
int roll3 = dice.Next(50, 101);

Console.WriteLine($"First roll: {roll1}");
Console.WriteLine($"Second roll: {roll2}");
Console.WriteLine($"Third roll: {roll3}");














