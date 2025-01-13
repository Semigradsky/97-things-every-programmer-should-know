# Escolha suas ferramentas com cuidado

Aplicações modernas raramente são construídas do zero. Elas são montadas usando ferramentas existentes - componentes, bibliotecas e frameworks - for um excelente número de razões:

- Aplicações crescem em tamanho, complexidade e sofisticação, enquanto que o tempo disponível para desenvolvê-las reduz. Fazemos melhor uso do nosso tempo como desenvolvedores se nos concentramos mais na escrita de código do domínio de negócios do que código de infraestrutura.

- Componentes muito usados e frameworks tem provavelmente menos bugs do que aqueles desenvolvidos em casa.

- Existe uma grande quantidade de software de altoa qualidade disponível na internet, que significa menores custos de desenvolvimento e maior chance de encontrar desenvolvedores com o interesse e expertise necessário.

- Desenvolvimento de software e sua manutenção é um trabalho humano intensivo, então comprar pode ser mais barato que construir.

No entanto, escolher a combinação correta de ferramentas para sua aplicação pode ser uma tarefa complicada que exige algum pensamento. Ao fazer um escolha, existem algumas coisas que você deve ter em mente:

- Ferramentas diferentes podem depender de diferentes suposições sobre o seu contexto - por exemplo, infraestrutura circundante, modelo de controle, modelo de dados, protocolos de comunicação, etc. - que podem levar à um desalinhamento arquitetural entre a aplicação e as ferramentas. Tal desalinhamento leva à hacks e atalhos que podem tornar o código mais complexo que o necessário.

- Ferramentas diferentes possuem diferentes ciclos de vida, e atualizar uma delas pode se tornar uma tarefa extremamente difícil e demorada visto que as novas funcionalidades, mudanças de design ou mesmo correções de bugs podem causar incompatibilidades com outras ferramentas. Quanto maior o número de ferramentas pior o problema pode se tornar.

- Algumas ferramentas requerem muita configuração, geralmente por meio de um ou mais arquivos XML, que podem sair do controle muito facilmente. A aplicação pode acabar parecendo como se tivesse sido escrita em XML mais algumas poucas linhas estranhas de código em alguma linguagem de programação. A complexidade configuracional irá tornar a aplicação difícil de manter e de evoluir.

- Dependências de fornecedores ocorrem quando o código que depende fortemente de algum produto do fornecedor acaba sendo restrito por eles em várias áreas: capacidade de manutenção, performance, habilidade de evoluir, preço, etc.

- Se você planeja usar software livre, você pode descobrir que ele não é de fato livre. Você pode necessitar comprar suporte comercial, que não será necessariamente barato.

- Termos de licença importam, mesmo para software livre. Por exemplo, em algumas empresas não é aceitável usar software licenciado sob a licença GNU por causa da sua natureza viral - ou seja, software desenvolvido com ele deve ser distribuído junto com seu código-fonte.

Minha estratégia pessoal para mitigar esse problemas é começar pequeno usando somente as ferramentas que são absolutamente necessárias. Usualmente o foco inicial é remover a necessidade de se envolver em programação de infraestrutura de baixo nível (e problemas)
, por exemplo, usando algum middleware ao invés de usar sockets puros para aplicações distribuídas. E adicionar mais ferramentas se necessário. Eu também tendo isolar as ferramentas externas dos meus objetos do domínio de negócios por meio de interfaces e organização de camadas, de forma que eu possa mudar a ferramenta se necessário com uma pequena quantidade de problemas. Um efeito positivo dessa abordagem é que eu geralmente acabo lidando com aplicações menores que usam menos ferramentas externas que originalmente previsto.

Por [Giovanni Asproni](http://programmer.97things.oreilly.com/wiki/index.php/Giovanni_Asproni)