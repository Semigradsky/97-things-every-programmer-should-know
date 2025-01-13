# Desenvolva usando a linguagem do domínio de negócios

Veja duas bases de código. Em uma delas você verá:

```
if (portfolioIdsByTraderId.get(trader.getId())
  .containsKey(portfolio.getId())) {...}
```
Você irá coçar sua cabeça, se perguntando o que esse código faz. Pode parecer que está obtendo um identificador de um negociador ("trader"), usando-o para obter um mapa de, veja só, aparentemente um mapa de mapas e então verificar se outro identificador de um objeto de portfólio existe no mapa mais interno. Você irá coçar sua cabeça ainda mais. Veja a declaração do portfolioIdsByTraderId e descubra isso:

```
Map<int, Map<int, int>> portfolioIdsByTraderId;
```

Gradualmente você passa a notar que pode ser algo relacionado com a possibilidade de um negociador ter acesso a um portfólio específico. E, é claro, você irá encontrar o mesmo fragmento - ou mais provavelmente um fragmento similar mas sutilmente diferente - sempre que alguma coisa se importa sobre se um negociador tem acesso à um portfólio específico.

Em outra base de código você pode se deparar com isso:

```
if (trader.canView(portfolio)) {...}
```

Nenhuma confusão mental. Você não precisa saber como o negociador sabe. Talvez exista um desses mapas de mapas embutido em algum lugar interno. Mas isso é preocupação do negociador e não sua.

Qual dessas duas bases de código você preferiria trabalhar?

Há muito tempo atrás tínhamos somente estruturas de dados muito básicas: bits e bytes e caracteres (na verdade apenas bytes mas nós fingimos que são letras e pontuações). Númerosdecimais eram um pouco traiçoeiros porquece nossos números de base 10 não funcionam muito bem em binário, de forma que tínhamos vários tamanhos de tipos de ponto flutuante. Então surgiram os arrays e strings (na verdade apenas arrays diferentes). Então surgiram as pilhas e filas e tabelas hash e listas ligadas e listas de alternações e várias outras esturutras de dados empolgantes que *não existem no mundo real*. "A ciência da computação" era sobre dispender muito esforço para mapear o mundo real nessas estruturas de dados restritivas. Os verdadeiros gurus podem até se lembrar como eles fizeram isso um dia.

Então surgiram os tipos de dados definidos pelos usuários (ou tipos abstratos de dados)! OK, isso não é novidade, mas mudou o jogo de alguma forma. Se o seu domínio contém conceitos como negociadores e portfólios, você pode modelá-los com tipos chamados, veja só, negociadores e portfólio. Mas, mais importante do que isso, você pode modelar *relações entre eles* usando termos do domínio também.

Se você não programa usando os termos do domínio você está criando um entendimento tácido (leia: secreto) que *este* int aqui significa uma forma de identificar um negociador, enquanto *aquele* int ali significa uma maneira de identificar um portfólio. (Melhor seria não misturar os dois!) E se você representa um conceito de negócio ("Alguns negociadores não são autorizados a visualizar alguns portfólios - isto é ilegal") com um bloco de código, como por exemplo uma relação em um mapa de chaves, você não está facilitando a vida dos auditores ou dos responsáveis pelo compliance.

O próximo programador pode não conhecer esse segredo, então porque não torná-lo explícito? Usar uma chave como parâmetro de busca de uma outra chave que executa uma varificação de existência não é terrivelmente óbvio. Como alguém é esperado supor quando uma regra de negócio está inflingindo algum conflito de interesse está implementada?

Tornar os conceitos do domínio de negócio explícitos no seu código significa que outros programadores podem coletar a *inteção* do seu código muito mais facilmente do que tentar regurgitar um algoritmo naquilo que eles entendem sobre um domínio. Também significa que quando o domínio de negócio evolui - o que acontecerá à medida que seu entendimento do domínio cresce - você estará em uma boa condição para evoluir o código. Junto com um bom encapsulamento do código, chances existem que essa regra existirá em um único local no código, e que você pode alterá-la sem que qualquer código dependente saiba.

O programador que chegar alguns meses depois para trabalhar no mesmo código irá te agradecer. Esse programador pode ser você.

Por [Dan North](http://programmer.97things.oreilly.com/wiki/index.php/Dan_North)