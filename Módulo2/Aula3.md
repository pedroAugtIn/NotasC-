Armazenar e iterar em sequências de dados usando matrizes e a instrução foreach em C#.

As matrizes em C# permitem armazenar sequências de valores em uma única estrutura de dados. Imagine uma única varíavel podendo conter vários valores.
Quando você tiver uma variável que armazena todos os valores, poderá classificá-los, reverter a ordem deles, executar loop em cada valor, inspecioná-los individualmente e assim por diante.

-O que é uma matriz?
É um tipo especial de variável que pode conter vários valores do mesmo tipo de dados. A sintaxe da declaração é ligeiramente diferente porque é necessário especificar o tipo de dados e o tamanho da matriz.


Exemplo: 
string[] fraudulentOrderIds = { "A123", "B456", "C789"};

-Usar a propriedade length na matriz:
Dependendo de como a matriz é criada, você não sabe quantos elementos ela contém. Para determinar o tamanho de uma matriz, você pode usar o propriedade length.
OBS: A propriedade length de uma matriz não começa no zero.

Recapitulação
Aqui estão as coisas mais importantes a serem lembradas ao trabalhar com matrizes:

Uma matriz é uma variável especial que contém uma sequência de elementos de dados relacionados.
Você deve memorizar o formato básico de uma declaração de variável de matriz.
Acesse cada elemento de uma matriz para definir ou obter seus valores usando um índice baseado em zero dentro de colchetes.
Se você tentar acessar um índice fora dos limites da matriz, será gerada uma exceção de runtime.
A propriedade Length é uma maneira programática de determinar o número de elementos em uma matriz.

-Executar um loop em uma matriz usando o foreach:
Uma maneira simples e limpa de iterar através dos elementos de uma matriz. A instrução foreach processa os elementos da matriz em ordem de índice crescente, começando no índice 0 e terminando no índice comprimento - 1. 
Ex:
string[] names = { "Rowena", "Robin", "Bao"};
foreach (string name in names)
{
    Console.WriteLine(name);
}

Recapitulação
Lembre-se dos seguintes tópicos sobre instruções foreach e valores incrementais que você aprendeu nesta unidade:

Use a instrução foreach para iterar em cada elemento de uma matriz, executando o bloco de código associado uma vez para cada elemento da matriz.
A instrução foreach define o valor do elemento atual na matriz como uma variável temporária, que pode ser usada no corpo do bloco de código.
Use o operador de incremento ++ para adicionar 1 ao valor atual de uma variável.


String.StartsWith(). - utilizado para determinar se um elemento começa com determinado caracter.
Ex:
string name = "Bob";
if (name.StartsWith("B"))
{
    Console.WriteLine("The name starts with 'B'!");
}

Parte final:

string[] fraudulents = {"B123", "C234", "A345", "C15", "B177", "G3003", "C235", "B179"};
foreach (string items in fraudulents)
{
   if(items.StartsWith("B")){
    Console.WriteLine(items);
   }
}