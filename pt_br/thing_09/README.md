# Confira seu próprio código antes de acusar os outros

Todos nós desenvolvedores temos dificuldade em acreditar que nosso próprio código está quebrado. É tão improvável que achamos que deva ser o compilador que tem um erro.

Quando na verdade é muito, muito improvável que o código está falhando por um bug no compilador, interpretador, sistema operacional, servidor de aplicação, banco de dados, gerenciador de memória ou qualquer outra peça de software. Sim, esses bugs existem, mas eles são bem menos comuns do que nós gostamos de acreditar.

Tive uma vez um problema genuíno com o compilador otimizando uma variável de uma estrutura de repetição, mas eu pensei que meu compilador ou sistema operacional tinha um bug em uma frequência muito maior. Já gastei muito do meu próprio tempo, tempo da equipe de suporte e tempo da gestão no processo apenas para me sentir menos idiota cada vez que descobria que o erro era meu no final das contas.

Assumir que as ferramentas são amplamente usadas, maduras e empregadas em várias stacks de tecnologia ajuda a entender que existe pouca razão para duvidar da sua qualidade. Claro, se a ferramente está nas suas versões iniciais, ou usada por poucas pessoas mundialmente, ou uma peça de software pouco baixada, versão 0.1, software de código aberto, existe boas razões para suspeitar. Igualmente uma versão alpha de um software comercial deve ser considerada suspeita. 

Visto que bugs de compiladores são raros, você deve dedicar sua energia e tempo em encontrar seu próprio erro. Todos os conselhos sobre depuração se aplicação, assim, isole o problema, crie chamadas auxiliares, introduza testes; cheque as convenções de chamadas de funções, bibliotecas compartilhadas e números de versão; explique para alguém; olhe para pilha corrompida e tipos de variáveis incoerentes; teste o código em diferentes máquinas e diferentes configurações de compilação. tais como debug e release.

Questione suas próprias suposições e as dos seus colegas. Ferramentas de diferentes empresas devem ter diferentes suposições ou premissas embutidas nelas - assim como diferentes ferramentas da mesma empresa. 
Quando alguém está relatando um problema que você não pode replicar, vá e veja o que ele está fazendo. Ele pode estar fazendo algo que você nunca pensou ou fazendo algo numa ordem diferente.

Como uma regra pessoal se eu tenho um bug que não consigo resolver e estou começando a pensar que é o compilador, é tempo de olhar a pilha em busca de dados corrompidos. Isso é especialmente verdade se ao adicionar código de tracing o problema muda de lugar.

Problemas multi-thread são outra fonte de bugs que causam cabelos brancos e induzem desespero com o computador. Todas as recomendações para favorecer código simples são multiplicadas quando se trata de um sistema multi-thread. Depuração e testes unitários não podem ser vistos como confiáveis para encontrar esses bugs com qualquer nível de consistência, assim a simplicidade de design é essencial.

Assim antes de correr para acusar o compilador, lembre-se do conselho do Sherlock Holmes: "Uma vez que eliminou o impossível, o que sobra, não importa quão improvável, deve ser a verdade" e prefira ele ao invés da versão do Dirk Gently: "Uma vez que eliminou o improvável, o que sobra, não importa quão impossível, deve ser a verdade.

Por [Allan Kelly](http://programmer.97things.oreilly.com/wiki/index.php/Allan_Kelly)
