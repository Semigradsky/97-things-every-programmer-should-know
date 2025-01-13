# Esteja ciente da sua parte no todo

Era meu primeiro projeto na empresa. Tinha concluído minha graduação recentemente e estava ansioso para provar meu valor e fazia horas extras todos os dias para navegar pelo código existente. À medida que eu avançava na minha primeira funcionalidade eu fui super cuidadoso em aplicar tudo aquilo que eu tinha aprendido - comentários, logging, separação de código compartilhado em bibliotecas quando possível e tudo mais. A revisão de código para qual eu me sentia tão preparado veio como um balde de água fria - o reuso era proibido!
Como poderia ser? Durante toda a faculdade o reuso era visto como o ápice da qualidade em engenharia de software. Todos os artigos que eu li, os livros-texto, os profissionais experientes que me ensinaram. Era tudo aquilo errado?

Descobri que eu estava esquecendo de algo crítico.

Contexto.

O fato que duas partes diferentes do sistema executavam alguma lógica da mesma forma significava menos do que eu pensava. Até o momento que eu havia extraído aquelas bibliotecas de código compartilhado, essas partes não eram co-dependentes. Cada uma evoluía independentemente. Cada parte poderia mudar sua lógica para adequar às necessidades do ambiente de negócios que dependiam daquele sistema. Aquelas quatro linhas de código similar eram acidentais - uma anomalia temporal, uma coincidência. Era, até que eu cheguei.

As bibliotecas de código compartilhado que eu criei criaram acoplamento entre as diferentes partes. Passos a serem tomados por um domínio de negócios não poderiam ser feitos sem primeiro sincronizar com o outro domínio. Custos de manutenção naquelas funções independentes eram desprezíveis mas a biblioteca comum passou a exigir uma ordem de magnitude a mais de testes.

Enquanto eu reduzia o número absoluto de linhas de código no sistema, eu havia aumentado o número de dependências. O contexto dessas dependências é crítico - estivessem restritas à um único local, seria justificável e teria valor positivo. Quando essas dependências não são mantidas em sincronia, seus tentáculos criam acoplamento que causam maiores preocupações ao sistema mesmo que o código por si mesmo parece correto.

Esses erros são traiçoeiros pois, no fundo, eles parecem uma ótima idéia. Quando aplicados ao contexto correto, essas técnicas são valiosas. No contexto errado, elas aumentam o custo ao invés de prover valor. Hoje, quando entro em contato com uma base de código existente sem ter conhecimento do contexto em que as várias partes serão usadas, eu sou muito mais cauteloso com aquilo que deva ser compartilhado entre diferentes partes.

Esteja ciente de sua parte no todo. Cheque seu contexto. Somente então prossiga. 

Por [Udi Dahan](http://programmer.97things.oreilly.com/wiki/index.php/Udi_Dahan)