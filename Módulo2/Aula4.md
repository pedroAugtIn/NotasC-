-Escolher nomes de variáveis que sigam as regras e convenções
Regras impostas pelo compilador do C#:
Os nomes de variáveis podem conter caracteres alfanuméricos e o caractere de sublinhado. Caracteres especiais como jogo da velha #, o traço - e o cifrão $ não são permitidos.
Os nomes de variáveis precisam começar com uma letra alfabética ou um sublinhado, não um número. Os desenvolvedores usam o sublinhado para uma finalidade especial, portanto, tente não usá-lo por enquanto.
Nomes de variável não podem ser uma palavra-chave do C#. Por exemplo, essas declarações de nome de variável não serão permitidas: float float; ou string string;.
Os nomes de variável diferenciam maiúsculas de minúsculas, o que significa que string MyValue; e string myValue; são duas variáveis diferentes.

Pratique a adoção dessas convenções e torne-as parte do seu próprio repertório de codificação.

Os nomes de variável devem usar o camel case, que é um estilo de escrita que usa uma letra minúscula no início da primeira palavra e uma letra maiúscula no início de cada palavra subsequente. Por exemplo: string thisIsCamelCase;.
Nomes de variável devem ser descritivos e significativos no aplicativo. Escolha um nome para a variável que represente a particularidade dos dados que ela manterá (não o tipo de dados). Por exemplo, bool orderComplete; e NÃO bool isComplete;.
Os nomes de variável devem ser uma ou mais palavras inteiras unidas. Não use contratações porque o nome da variável pode não ser claro para outras pessoas que estão lendo seu código. Por exemplo, decimal orderAmount; e NÃO decimal odrAmt;.
Nomes de variável não devem incluir o tipo de dados da variável. Você pode vir a receber alguns conselhos de usar um estilo como string strMyValue;. Esse era um estilo popular há alguns anos. No entanto, a maioria dos desenvolvedores não segue mais esse conselho e há bons motivos para isso.

Exemplos:
char userOption;
int gameScore;
float particlesPerMillion;
bool processedCustomer;

Como comentar em um código:
// meu comentário.

é útil em três situações:

Quando você quer deixar uma observação sobre a intenção de uma passagem de código. Pode ser útil incluir comentários de código que descrevem a finalidade ou o processo de pensamento quando você está escrevendo um conjunto particularmente desafiador de instruções de codificação. Isso facilitará muito seu trabalho no futuro.
Quando você deseja remover temporariamente o código do aplicativo para tentar uma abordagem diferente, mas ainda não está convencido de que sua nova ideia funcionará. Você poderá comentar o código, escrever o novo código e, quando estiver convencido de que o novo código funcionará da maneira desejada, você poderá excluir o antigo (código comentado) com segurança.
Adicionar uma mensagem como TODO para lembrá-lo de examinar uma determinada passagem de código posteriormente. Embora você deva usar isso criteriosamente, esse é uma abordagem útil. Você pode estar trabalhando em outro recurso e ler uma linha de código que desperta uma preocupação. Em vez de ignorar a nova preocupação, você pode marcá-la para investigação posterior.

Recapitulação
Os principais aprendizados deste exercício:

Use comentários de código a fim de deixar observações significativas para si mesmo sobre os problemas que cada trecho de código específico resolve.
Não use os comentários de código para explicar como funciona o C# ou a biblioteca de classes do .NET.
Use comentários de código ao experimentar temporariamente soluções alternativas até que você esteja pronto para confirmar a nova solução de código; nesse ponto, você poderá excluir o código antigo.
Nunca confie em comentários. Eles podem não refletir o estado atual do código após muitas alterações e atualizações.













