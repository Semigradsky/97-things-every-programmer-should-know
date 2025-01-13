# Conveniência não é uma qualidade

Muito tem se falado sobre a importância e os desafios do design de boas API's. É difícil acertar da primeira vez e é ainda mais difícil mudar depois. Muito parecido com a educação dos filhos. A maioria dos programadores experientes aprendeu que uma boa API segue um nível consistente de abastração, exibe consistência e simetria, e forma o vocabulário para uma linguagem expressiva. Aliás, estar consciente dos princípios não se traduz automaticamente em comportamento apropriado. Comer doces é ruim para você.

Ao invés de pregar do alto, eu quero selecionar uma estratégia de design de APIs particular, uma que eu encontro com frequência: o argumento da conveniência. Começa tipicamente com um dos 'insights' a seguir:

- Eu não quero que outras classes tenham que fazer duas chamadas separadas para executar essa atividade.
- Porque eu faria outro método se ele é quase igual ao método existente? Adicionarei apenas um 'switch'.
- Veja, é muito fácil: se o segundo parâmetro do tipo string termina com ".txt", o método automaticamente assume que o primeiro parâmetro é um nome de arquivo, de forma que eu não preciso de dois métodos.

Embora sejam bem-intencionados, tais argumentos são sujeitos a diminuir a legibilidade do código usando a API. Uma invocação de método como:

```
parser.processNodes(text, false);
```

é virtualmente sem sentido sem que se conheça a implementação ou ao menos a documentação seja consultada. Esse método foi provavelmente projetado para a conveniência do implementador em oposição à conveniência do usuário - "Eu não quero que o usuário tenha que fazer duas chamadas separadas" traduzido em "Eu não quis escrever dois métodos separados." Não existe nada fundamentalmente errado com a conveniência se ela for construída para ser o antídoto ao tédio, bagunça ou estranhamento. Entretanto, se pensarmos um pouco mais cuidadosamente, o antídodo para esses sintomas é a eficiência, consistência e elegância, não necessariamente a conveniência. Espera-se que APIs escondam a complexidade interna, de forma que podemos realisticamente esperar que bons designs de API exijam algum esforço. Um método grande pode ser certamente mais conveniente de escrever que um conjunto bem planejado de operações, mas seria mais fácil de usar?

A métafora da API como uma linguagem pode nos guiar em direção à melhores decisões de projeto nessas situações. Uma API deve prover uma linguagem expressiva, que dà à próxima camada vocabulário suficiente para fazer e responder perguntas úteis. Isso não implica que ela deveria fornecer apenas um método, ou verbo, para cada questão relevante. Um vocabulário diverso permite-nos expressar sutilezas em significado. Por exemplo, nós preferimos correr ao invés de andar, mesmo que as duas possam ser vistas como a mesma operação, executadas em diferentes velocidades. Um vocabulário de API consistente e bem planejado torna o código fácil de entender e expressivo na próxima camada acima. Mais importante, um vocabulário composto permite outros programadores usarem a a API em formas que você pode não ter antecipado - uma grande conveniência para os usuários da API! Na próxima vez que você se ver tentado a mesclar várias coisas em um único método da API, lembre-se que a língua inglesa não tem uma palavra para `MakeUpYourRoomBeQuietAndDoYourHomeWork`, mesmo que isso pareça importante para tal operação frequente.

Por [Gregor Hohpe](http://programmer.97things.oreilly.com/wiki/index.php/Gregor_Hohpe)