# Não tenha vergonha dos seus dados de teste

> *Eu estava atrasado. Coloquei algum dado esdrúxulo para testar o layoyt da página que eu estava trabalhando.*

> *Apropriei o nome dos membros do The Clash para dar nomes aos usuários. Nomes de empresas? Títulos de canções do the Sex Pistols poderiam servir a esse propósito. Agora eu preciso de algumas siglas de ações - apenas quatro letras em maiúsculas.*

> *Usei aquelas palavras de baixo calão.*

> *Parecia inofensivo. Apenas para me divertir, e talvez também os outros desenvolvedores do dia seguinte antes que eu colocasse a fonte de dados reais.*

> *No dia seguinte, o gerente de projetos obteve algumas capturas de tela para fazer uma apresentação.**

A história da programação é rica de exemplos dessas histórias de guerra. Coisas que os desenvolvedores e designers pensaram que ninguém mais veria se tornaram visíveis inesperadamente.
O tipo de vazamento pode variar mas, quando acontece, pode ser mortal para a pessoa, time ou empresa responsável. Os exemplos incluem:

- Durante uma reunião de status, um cliente clica no botão que estava pendente de implementação. A mensagem de alerta dizia: "Não clique no botão novamente, seu idiota."
- Um programador mantendo um sistema legado foi avisado para incluir uma caixa de diálogo de erro e decide usar a saída do sistema de logs interno como conteúdo. Usuários são surpreendidos com mensagens como "Santa falha de comit do banco de dados, Batman!" quando alguma coisa quebra.
- Alguém mistura as interfaces de administração do ambiente de teste e de produção e faz algumas entradas de dados "engraçados". Os clientes visualizam um serviço de 1 milhão de dólares em desconto na loja online. O nome? Massagista pessoal com formato do Bill Gates"

Citando um ditado antigo que diz que "uma mentira pode viajar ao redor do mundo enquanto a verdade ainda está calçando seus sapatos", atualmente um deslize pode viajar pelo Twitter antes que um desenvolvedor no fuso horário correto esteja acordado para fazer qualquer correção.

Mesmo seu código fonte não é necessariamente livre de escrutínio. Em 2004, quando um arquivo compactado do código fonte do Windows 200 apareceu em redes de compartilhamento de arquivos, algumas pessoas vasculhou em busca de palavras profanas, insultos e [outros conteúdos engraçados](http://www.kuro5hin.org/story/2004/2/15/71552/7795). (O comentário `// TERRÍVEL HORRÍVEL NADA BOM MUITO RUM HACK` se tornou usual no meu uso ocasional desde então!)

Em resumo, ao escrever qualquer texto no seu código - seja comentário, logs, caixas de diálogo ou dados de teste - sempre se pergunte como irá parecer se esse texto se tornar público. Economizará alguns vexames ao redor.

Por [Rod Begbie](http://programmer.97things.oreilly.com/wiki/index.php/Rod_Begbie)