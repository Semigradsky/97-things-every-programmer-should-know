# Automatize seus padrões de código

Já aconteceu com você, eu sei. No início de um projeto, todos têm boas intenções  - pode chamar de resoluções de "projeto novo". Muito frequentemente, muitas dessas resoluções são escritas em documentos. Aqueles sobre código acabam na seção de padrões de código do projeto. Durante a reunião de lançamento, o desenvolvedor líder percorre o documento e, no melhor caso, todos concordam que tentarão seguir os padrões. Uma vez que o projeto se inicia, no entanto, essas boas intenções são abandonadas, uma por vez. Quando o projeto é finalmente entregue o código parece uma bagunça,  e ninguém parece entender como foi que chegou nesse ponto.

Onde foi que as coisas deram errado? Provavelmente já na reunião de lançamento. Alguns membros não prestaram a devida atenção. Outros não entenderam o ponto. Ainda pior, alguns discordaram e já inciaram o planejamento da rebelião aos padrões de código. Finalmente, alguns entenderam o ponto e concordaram mas, quando a pressão no projeto subiu, eles abriram mão de algo. Código bem formatado não te confere pontos com um cliente que quer mais funcionalidade. Aliás, seguir um padrão de códigoode ser uma tarefa muito chata se não for automatizada. Tente, por exemplo, indentar manualmente uma classe bagunçada para experimentar.

Mas se eu problema porque insistimos em ter um padrão de código? Uma razão para formatar o código uniformemente é que ninguém deve possuir um pedaço de código apenas pelo estilo de formatação particular. Desejamos prevenir que desenvolvedores usem certos anti-padrões, para assim evitar certos bugs. No final, um padrão de código deve tornar o trabalho mais fácil e auxiliar na manutenção da velocidade de desenvolvimento do início ao fim do projeto. Assim, todos devem concordar com o padrão estabelecido - não contribui se um desenvolvedor usar três espaços para indentacao enquanto que outro use quatro. 

Existe uma grande diversidade de ferramentas que podem ser usadas para prodizir relatorios de qualidade de codigo e para documentar e manter o padrão de código mas essa não é a história completa. Os padrões devem ser automatizados e verificados onde possível. Aqui alguns exemplos:

- Certifique-se que a formatação de código é parte do processo de compilação/  build, de forma que todos rodem automaticamente toda vez que compilação o código. 
- Use ferramentas de análise estática de código para detectar anti-padrões indesejáveis no código. Se algum anti-padrao for encontrado, quebre o processo de compilação. 
- Aprenda a configurar essas ferramentas de forma que você possa verificar seus anti-padrões que são particulares ao seu projeto.
- Não meça apenas a cobertura de testes mas cheque os resultados também. Novamente,  quebre o processo de compilação se a cobertura for muito baixa.

Tente fazer isso para tudo aquilo que você considerar importante. Você não será capaz de automatizar tudo o que é importante. Para aqueles itens que não podem ser verificados ou marcados automaticamente,  considere-os como um guia suplementar aos padrões de código automatizado mas aceite que você é seus colegas podem não seguir esses itens suplementares tão diligentemente. 

Finalmente, um padrão de código deve ser dinâmico e não estático. À medida que o projeto evolui, as necessidades do projeto mudam e aquilo que parecia inteligente no início não será necessariamente uma escolha inteligente alguns meses depois.


Por [Filip van Laenen](http://programmer.97things.oreilly.com/wiki/index.php/Filip_van_Laenen)
