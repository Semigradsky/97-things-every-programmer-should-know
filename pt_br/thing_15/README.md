# Programando com um motivo

Tentar argumentar sobre corretude de sofware através de resultados manuais numa prova formal que é mais lenta que o código é mais provável que contenha erros que o próprio código em si. Ferramentas automatizadas são preferíveis, mas isso não é sempre possível. O que descrevo a seguir é o caminho do meio: argumentar sobre corretude através de uma abordagem semi-formal.

A abordagem fundamental é dividir todo o código sob consideração em pequenas seções - desde uma linha única, tal como uma chamada de função, a blocos de menos de 10 linhas - e investigar sua corretude. Os argumentos necessitam ser fortes o suficiente para convencer seu companheiro programador que atue como advogado do diabo.

Uma seção deve ser escolhida de forma que em cada ponto o *estado do programa* (em especial, o contador do programa e todos os valores dos objetos "vivos") satisfaçam uma propriedade descrita de forma simples, e que a funcionalidade daquela seção (transformação de estado) seja fácil de descrever como uma tarefa simples - isso fará a argumentação mais simples. Tais propriedades generalizam conceitos como *pré-condições* e *pós-condições* para funções, e *invariantes* para laços de repetição e classes (com respeito às suas instâncias). Buscar atingir seções que sejam independentes umas das outras quanto possível simplifica a argumentação e é indispensável quando essas seções devam ser modificadas posteriormente.

Muitas das práticas de desenvolvimento estabelecidas (embora não sejam igualmente aplicadas na prática) e consideradas 'boas' tornam a argumentação pela corretude mais fácil. Assim, uma vez que se busque verificar a corretude do código, seu pensamento ao escrever novos códigos move-se para um melhor estilo e estrutura. Não surpreendentemente, a maioria dessas práticas podem ser checadas por analisadores estáticos de código:

- Evite usar instruções GO TO que geram interdependência entre partes muito distantes de código.
- Evite usar variáveis globais mutáveis que também causam que todas as seções que as usam sejam interdependentes.
- Toda variável deve ter o menor escopo possível. Por exemplo, um objeto local pode ser declarado imediatamente antes do seu primeiro uso.
- Torne objetos *imutáveis* quando relevante.
- Torne o código legível através do uso de espaçamento, tanto horizontal quanto verfical. Por exemplo, alinhando estruturas relacionadas e usando linhas em branco para separar duas seções.
- Torne o código auto-documentável através da boa escolha de nomes descritivos para objetos, tipos e funções, etc.
- Se precisar de uma seção aninhada, crie uma função para ela.
- Faça que suas funções sejam curtas e focadas numa única tarefa. O limite antigo de *24 linhas* ainda se aplica. Embora o tamanho e a resolução das telas tenha se alterado, nada mudou na cognição humana desde os anos 1960.
- Funções devem ter poucos parâmetros (quatro é um bom limite superior). Isso não restringe a comunicação de dados para funções: através do agrupamento de parâmetros relacionados em um único objeto obtém-se o benefício de *invariantes de objeto* e salva na argumentação em quesitos como sua coerência e consistência.
- Geralmente, cada unidade de código, desde um bloco à uma biblioteca, deve ter uma *interface pequena*. Menos comunicação reduz a argumentação exigida. Isso significa que *acessores de busca de propriedade* que retornam o estado interno são um passivo - não pergunte a um objeto pela informação a ser trabalhada. Ao invés disso, peça ao objeto para fazer o trabalho com a informação que ele já possui. Em outras palavras, *encapsulamento* é tudo - e somente - sobre *interfaces pequenas*.
- Para preservar os *invariantes* de classe, usos de "acessores de configuração de propriedade* devem ser evitados, visto que eles permitem que os invariantes sejam invalidados.

A argumentação pela corretude de código traz como vantagem uma maior compreensão. Comunique os aprendizados que você adquiriu para o benefício de todos.

Por [Yechiel Kimchi](http://programmer.97things.oreilly.com/wiki/index.php/Yechiel_Kimchi)
