# Não bata no seu programa na posição errada

Uma vez escrevi um quiz falso de C++, no qual eu satiricamente sugeri a seguinte estratégia para tratamento de exceções:

> Espalhando um número suficiente de estruturas `try...catch` através da nossa base de código, algumas vezes somos capazes de prevenir nossas aplicações de abortar. Pensamos no estado resultando como "posicionar o defundo na posição vertical".

A despeito da minha leviandate, eu estava na verdade resumindo uma lissão que recebi ajoelhoado aos pés da Dama da Má Experiência.

Era uma classe para uma aplicação básica, para uma biblioteca de C++ caseira. Ela sofreu de várias tentativas de diferentes programadores ao longo dos anos: Nenhuma das mãos está efetivamente limpa. Contina código para lidar com todas as exceções para todos os cenários imagináveis. Com apoio do nosso líder técnico, decidimos, ou sentimos (*decidimos* implica mais análise que a que colocamos na construção desse monstro), que uma instância dessa classe deveria viver para sempre ou morrer na tentativa.
Para esse fim, intercalamos múltiplos tratamentos de excecão. Nós misturamos ao tratamento estruturado do Windows com o tipo nativo (lembra do `__try...__except` in C++? Eu também não). Quando as coisas se comportaram de forma insperada, tentamos chamar a mesma função ou método novamente, filtrando ainda mais os parâmetros. Em retrospectiva, gosto de pensar que ao escrever uma estrutura de tratamento de exceção `try...catch` dentro da sentença catch de um outro tratamento de exceção, algum tipo de consciência aparece para indicar que eu posso ter acidentalmente tomado uma estrada escorregadia e chegado ao nível lunático. Entretanto, isso é provavelmente sabedoria retrospectiva.
Não preciso dizer que quando algo dá errado nas aplicações baseadas nessa classe, as evidências todas somem como vítimas da máfia em um porto, não deixando nenhum rastro de bolhas para indicar o que houve, e nem as rotinas de *dump* que se esperava registrar o desastre foram acionadas. Eventualmente, registramos o que foi feito e experimentamos uma vergonha. Substituímos a bagunça completa com um mecanismo mínimo e robusto de relatórios. Mas isso apenas após vários *crashes*.

Eu não te importunaria com isso - certamente ninguém mais poderia ser tão estúpido como nós formos - mas devido a uma discussão online que tive recentemente com um rapaz cujo título acadêmico declarava que ele já devia saber.
Estávamos discutindo um código Java em um transação a remota. Se o código falhase, ele argumentava, ele deve capturar e bloquear a exceção *in situ*. ("E então fazer o quê com ela?" Eu perguntei. "Cozinhá-la para a janta?")

Ele citou a regra dos designers de interface: NUNCA DEIXE O USUÁRIO VER UM RELATÓRIO DE EXCEÇÃO, como se isso tivesse esgotado o assunto e com tudo em letras maiúsculas. Pensei que se ele pudesse ter sido responsável pelo código em um desses caixas de banco que dão tela azul e decoram posts de blogs depreciativos e tivesse sido permanentemente traumatizado.

De qualquer forma, se encontrá-lo, balance a cabeça, sorria e siga adiante à medida que você desvie para a saída.

Por [Verity Stob](http://programmer.97things.oreilly.com/wiki/index.php/Verity_Stob)