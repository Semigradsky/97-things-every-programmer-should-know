# Aplique princípios de programação funcional

Programação funcional tem desfrutado de um novo interesse da comunidade de programação "mainstream". Parte da razão é devido às "propriedades emergentes do paradigma funcional estarem preparadas para resolver os desafios colocados pela mudança da nossa indústria em direção ao uso de processadores de múltiplos núcleos. Entretanto, enquanto esse é um uso certamente importante da programação funcional, não é a razão que esse texto tenta te oferecer para conhecer progração funcional.

O domínio do paradigma da programação funcional pode melhorar significativamente a qualidade do código que você escreve em outros contextos. Se você entender profundamentamente e aplicar esse paradigma, seus projetos irão exibir um elevado grau de *transparência referential*.


Transparência referencial é uma propriedade bastante desejável: ela implica que funções produzem consistentemente os mesmos resultados para a mesma entrada, independente de quando e onde essas funções são invocadas. Ou seja, a função depende menos - idealmente não depende - dos efeitos colaterais de um estado mutável.

Uma causa importante de defeitos em código imperativo é atribuída às variáveis mutáveis. O leitor desse texto já deve ter investigado porque algum valor não é o mesmo que o esperado numa dada situação. A semântica de visibilidade pode ajudar a miticar esses defeitos traiçoeiros, ou pelo menos restringir severamente sua localização, mas a verdadeira culpa reside no fato de design de código que aplicam mutabilidade indiscriminada.

E nós certamente não recebemos muita ajuda da indústria nesse aspecto. Introduções à orientação à objetos promovem tacitamente tais designs, porque elas geralmente mostram exemplos compostos por grafos de objetos de vidade relativamente longa que ativam métodos que causam mutações mútuas, que podem ser perigosas. Entretanto, com um design cuidadoso de código dirigido por testes, particularmente quando a regra de mockar papéis e não objetos é seguida ["Mock Roles, not Objects"](http://www.jmock.org/oopsla2004.pdf), a mutabilidade desnecessária é eliminada.

O resultado líquido é um projeto que tipicamente possui melhor responsabilidade nas alocações com mais numerosas e menores funções que atuam nos argumentos passados para elas, ao invés de referenciar variáveis membro mutáveis. Existirão menos defeitos, e estes serão geralmente mais simples de depurar, porque é mais fácil de localizar onde um valor incorreto foi introduzido nesses designs de código do que deduzir o contexto particular que resultou na atribuição de valor errônea. Isso se soma a um grau mais elevado de transparência referencial, e nada é melhor para te ensinar essas idéias que aprender uma linguagem de programação funcional, onde esse modelo de computação é o padrão.

É claro que essa abordagem não é ótima para todas as situações. Por exemplo, em sistemas orientados a objeto, esse estilo geralmente produz melhores resultados quado acoplado ao desenvolvimento do modelo de domínio (ou seja, quando as colaborações servem para reduzir a complexidade das regras de negócio). O mesmo não se observa no desenvolvimento de interfaces de usuário.

Domine o paradigma da programação funcional de forma que você seja capaz de aplicar cuidadosamente as lições aprendidas em outros domínios. Seus sistemas de objetos irão ressoar com boa transparência referencial e serãos mais próximos aos seus pares funcionais do que muitos te farão acreditar. De fato, alguns afirmam que o ápice da programação funcionao e da orientação a objetos são meramente um reflexo um do outro, uma forma computacional de yin e yang.

Por [Edward Garson](http://programmer.97things.oreilly.com/wiki/index.php/Edward_Garson)