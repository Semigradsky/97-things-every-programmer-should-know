# Aja com Prudência

> *"O que quer que você empreenda, aja com prudência e considere as consequências" Anon*

Não importa o quão confortável um cronograma pareça no início de uma iteração, você não pode evitar estar sob pressão algumas vezes. Se você se encontrar tendo que escolher entre "fazer certo" e "fazer rápido" geralmente é mais atraente "fazer rápido" sob o entendimento de que você vai voltar e consertar mais tarde. Quando você faz essa promessa para você mesmo, seu time, e seu cliente, é isso mesmo que você quer dizer. Mas muitas vezes a próxima iteração trás novos problemas e você acaba focando neles. Esse tipo de trabalho adiado é conhecido como débito técnico e não é seu amigo. Especificamente, Martin Fowler chama isso de débito técnico deliberado em sua [taxonomia de débito técnico](http://martinfowler.com/bliki/TechnicalDebtQuadrant.html), que não deve ser confundido com débito técnico inadvertido.

Débito técnico é como um empréstimo: Você se beneficia disso no curto prazo, mas você tem que pagar juros sobre ele até que esteja totalmente pago. Atalhos no código tornam difícil de adicionar _features_ ou refatorar seu código. Eles são criadouros para defeitos e testes que falham com frequência. Quanto mais tempo você o mantiver, pior fica. No momento que você começa a realizar a correção original pode haver uma pilha inteira de decisões de design "não muito corretas" em camadas sobre o problema original, tornando o código muito mais difícil de refatorar e corrigir. De fato, muitas vezes apenas quando as coisas ficam tão ruins que você deve consertá-las, é que você realmente volta para consertar. E, então, muitas vezes é tão difícil corrigir que você realmente não pode pagar pelo tempo ou pelo risco.

Existem momentos que você deve criar débito técnico para cumprir um prazo ou implementar parte de uma _feature_. Tente não estar nessa posição, mas se a situação absolutamente demandar isso, vá em frente. Mas (e isso deve ser um grande MAS) você deve mapear o débito técnico e pagá-lo rapidamente ou as coisas irão rapidamente ladeira abaixo. Assim que você decidir se comprometer, escreva um cartão de tarefa ou registre isso no seu sistema de mapeamento de _issues_ para garantir que não seja esquecido.

Se você programar o pagamento do débito na próxima iteração, o custo será mínimo. Não resolver o débito vai gerar um acúmulo de juros e esses juros devem ser mapeados para tornar o custo visível. Isso enfatizará o efeito sobre o valor de negócio do débito técnico do projeto e permitirá a priorização adequada do pagamento. A escolha de como calcular e mapear os juros vai depender do projeto em particular, mas você deve mapeá-lo.

Resolva o débito técnico assim que possível. Seria imprudente fazer o contrário.

Por [Seb Rose's GitHub profile](https://github.com/sebrose) / [Seb Rose's LinkedIn Profile](https://www.linkedin.com/in/sebrose)

https://www.oreilly.com/library/view/97-things-every/9780596809515/ch01.html