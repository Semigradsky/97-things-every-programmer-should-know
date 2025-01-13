# A regra do escoteiro

Os escoteiros tem uma regra: "Sempre deixe o acampamento mais limpo do que encontrou." Se você encontrar sujeira no chão, limpe independentemente de quem causou a sujeira. Você melhora o ambiente intencionalmente para o próximo grupo de pessoas que forem acampar. Na verdade a forma original dessa regra, escrita por Robert Stephenson Smyth Baden-Powell, o pai do escoterismo, era "Tente deixar esse mundo um pouco melhor do que encontrou".

O que aconteceria se adotássemos uma regra similar em nossos códigos: "Sempre comite um módulo mais limpo que quando você começou a mexer." Não importa quem foi o autor original, o que aconteceria se sempre fizéssemos algum esforço, mesmo que pequeno, para melhorar o módulo. Qual seria o resultado?

Penso que se todos nós seguíssemos essa regra simples, seria o fim da deterioração inevitável dos nossos sistemas de software. Pelo contrário, nossos sistemas iriam melhorar gradualmente à medida que o tempo passasse. Veríamos *times* cuidando do sistema como um todo, ao invés de apenas indíviduos se preocupando com sua pequena parte individual.

Não penso que essa é uma regra muito difícil. Você não precisa fazer todo módulo perfeito antes de comitar. Você precisa apenas fazê-lo *um pouco melhor* do que quando começou. Claro, isso significa que qualquer código que *adicione* a um módulo deve ser limpo. Isso também significa que você limpará ao menos uma outra coisa antes de comitar novamente o módulo. Você pode simplesmente melhorar o nome de uma variáve, ou dividir uma grande funcão em duas funções menores. Você pode quebrar uma dependência circular, ou adicionar uma interface para desacoplar a política do detalhe.

Francamente, isso parece como senso comum para mim - como lavar as mãos após usar o banheiro ou colocar o seu lixo na lixeira ao invés de jogar no chão. O ato de deixar uma bagunça no código deveria ser considerado como socialmente inaceitável assim como é o ato de *jogar lixo no chão*. Deveria ser algo que *nunca é feito*.

Mas é ainda mais do que isso. Cuidar do seu próprio código é uma coisa. Cuidar do código do time é outra completamente diferente. Membros de times ajudam uns aos outros, e limpam as bagunças uns dos outros. Eles seguem a regra do escoteiro porque isso é bom para todos e não só para eles mesmos.

Por [Robert C. Martin (a.k.a. Uncle Bob)](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)