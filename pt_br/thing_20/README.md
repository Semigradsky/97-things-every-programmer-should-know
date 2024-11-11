# Implemente cedo e frequentemente

Resolver problemas de implementação e da instalação é deixado geralmente para o final de um projeto.
. Em alguns projetos, escrever as ferramentas de instalação é delegado a um engenheiro especializado em lançamentos que recebe a tarefa como um "mau necessário". Revisões e demonstrações são feitas de um ambiente cuidadosamente preparado para assegurar que tudo funciona. O resultado é que o time não absorve nenhuma experiência com o processo de implementação ou com o ambiente já implementado até que seja muito tarde para fazer mudanças.

O processo de instalação / implementação é a primeira coisa que o cliente vê, e um processo simples de instalação / implementação é o primeiro passo para ter um ambiente de produção confiável ou, ao menos, fácil de depurar. O software implementado é aquilo que o cliente irá ver. Ao não garantir que a implementação da aplicação seja feita corretamente, você irá gerar questões com seu cliente antes que eles usem seu software integralmente.

Começar seu projeto com um processo de instalação te dará tempo para evoluir o processo à medida que o ciclo de desenvolvmento de produto avança, e a chance de fazer mudanças no código da aplicação para tornar a instalação mais fácil. Rodar e testar o processo de instalação num ambiente limpo periodicamente também fornece uma checagem que você não assumiu premissas no código que dependenm do ambiente de desenvolvimento ou teste.
Deixar a implementação por último significa que o processo de implementação pode se tornar mais complicado para contornar as premissas no código. O que parecia uma grande idéia numa IDE, onde você tem controle total sobre um ambiente, pode fazer um processo de implementação muito mais difícil. É melhor saber todos os prós e contras mais cedo do que no último minuto.

Embora "estar apto para implementar" não pareça ter muito valor de negócio quando comparado à aplicação rodando num laptop do desenvolvedor, a verdade é que até que você possa demonstrar a aplicação no ambiente alvo, existe muito trabalho antes de entregar valor para o negócio. Se seu raciocínio para postergar a implementação porque ela é trivial, então faça a implementação de imediato visto que é de baixo custo. Se for muito complicada, ou se tiver muitas incertezas, faça o que faria com o código da aplicação: experimente, avalie, e refatore o processo de implementação à medida que for avançando.

O processo de instalação/desenvolvimento é essencial para a produtividade dos seus clientes ou do seu time de serviços profissional, de forma que você deve testar e refatorar esse processo à medida que você avança. Testamos e refatoramos o código fonte ao longo do projeto. O processo de implementação merece o mesmo tratamento.

Por [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)
