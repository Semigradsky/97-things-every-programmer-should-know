# Antes que você refatore

Em algum momento da carreira todo programador precisará refatorar código existente. Mas, antes que você faça isso, por favor pense sobre os seguintes aspectos que podem te economizar um tempo significativo (e sofrimento):

- *A melhor abordagem para reestruturação se inicia por entender a base de código existente e os testes escritos contra ela.* Isso irá te ajudar a entender as forças e fraquezas do código na sua forma atual, de forma que você mantenha os pontos fortes e evite os erros. Nós sempre pensamos que podemos melhorar o sistema existente... até que nós entregamos algo que não só não é melhor - ou até pior - que o código antigo porque falhamos em aprender com as falhas do sistema existente.

- *Evite a tentação de reescrever tudo.* É melhor reusar a maior quantidade de código possível. Não importa quão feio o código é, ele já foi testado, revisado e etc. Jogar fora código velho - especialmente se está em produção - significa que você está jogando fora meses (ou anos) de código testado e estressado que pode ter tido certos ajustes e correções de bugs que você não está ciente deles. Se você não leva isso em conta, o novo código que você escreve pode acabar mostrando os mesmos bugs misteriosos que foram corrigidos no código velho. Isso irá desperdiçar muito tempo, esforço e conhecimento adquirido ao longo dos anos.

- *Muitas mudanças incrementais são melhores que uma mudança massiva.* Mudanças incrementais permitem que você mensure o impacto no sistema mais facilmente através de feedbacks tais como testes. Não é nada agradável ver centenas de testes falhando depois de fazer uma mudança. Isso pode levar à frustração e pressão que podem se tornar em decisões ruins. Alguns testes falhando é uma situação mais fácil de lidar e fornece uma abordagem mais gerenciável.

- *Após cada iteração, é importante garantir que os testes existentes passem.* Adicione novos testes se os testes existentes não forem suficientes para cobrir as mudanças que você fez. Não jogue fora os testes do código antigo sem a devida consideração. No início esses testes podem parecer que não são aplicáveis ao seu novo design, mas pode ser valioso entender profundamente as razões pelas quais um teste em particular foi adicionado.

- *Preferências pessoais e ego não devem ficar no seu caminho.* Se algo não está quebrado, porquê corrigir? O estilo ou a estrutura do código não estar alinhado à sua preferência pessoal não é uma razão válida para reestruturar seu código. Pensar que você irá fazer um trabalho melhor que o programador anterior não é uma razão válida também.

- *Tecnologias novas não são razão suficiente para refatorar.* Uma das piores razões para refatorar é porque o código atual está muito defasado em relação às tecnologias que são modinha atualmente, e nós acreditamos que uma nova linguagem ou framework podem fazer as coisas muito mais elegantes. Ao menos que uma análise de custo benefício mostre que uma nova linguagem irá resultar em melhorias significativas em funcionalidade, facilidade de manutenção ou produtividade, é melhor deixar como está.

- *Lembre-se que humanos cometem erros.* Reestruturar o código não garante que sempre o novo código será melhor - ou mesmo tão bom quanto - que a tentativa anterior. Eu já vi e já participei de várias tentativas de reestruturação mal-sucedidas. Não é bonito mas é algo humano.

Por [Rajith Attapattu](http://programmer.97things.oreilly.com/wiki/index.php/Rajith_Attapattu)