# Não dependa da "Mágica que acontece aqui"

Se você olhar para qualquer atividade, processo ou disciplina a uma longa distância ela irá parecer simples. Gerentes sem nenhum experiência de desenvolvimento pensam que o que os programadores fazem é simples e programadores sem nenhuma experiência de gestão pensam o mesmo de seus gerentes.
Programação é algo que algumas pessoas fazem - em parte do tmepo. E a parte difícil - o pensar - é a parte menos visível e menos apreciada pelos não iniciados. Existiram muitas tentativas de eliminar a necessidade desse pensamento qualificado nas últimas décadas. Um dos mais antigos e mais memoráveis esforços foi feito por Grace Hopper para tornar as linguagens menos crípticas - que alguns previram iria remover a necessidade de programadores especialistas. O resultado (COBOL) contribuiu com a renda de muitos programadores nas décadas subsequentes.
A visão persistente que o desenvolvimento de software pode ser simplificado através da remoção da programação é, para os programadores que entendem o que está envolvido, obviamente ingênuo.

Em qualquer projeto existem muitas atividades que um programador individual não se envolve: levantamento de requisitos de usuários, obter aprovação de orçamentos, configurar o servidor de build, implementar a aplicação nos ambientes de QA e Produção, migração de negócios de processos ou programas antigos, etc.

Quando você não está ativamente envolvido nessas atividades existe uma tendência inconsciente de assumir que elas são simples e acontecem "por mágica". Enquanto a mágica continua acontecer é fantástico. Mas quando - é usualmente "quando" e não "se" - a mágica para o projeto entra em risco.

Eu conheci projetos que perderam semanas de tempo do desenvolvedor porque ninguém entendia como eles dependiam na "versão correta" de uma DLL carregada. Quando as coisas começaram a falhar intermitente os membros do time procuravam em todos os lugares antes que alguém notou que "uma versão errada" da DLL estava sendo carregada.

Outro departamento estava operando de forma suave - projetos entregues no prazo, nenhuma sessão de debuggin em altas horas, sem correções de emergências. Tão suave, de fato, que a alta liderança decidiu que as coisas "funcionavam sozinhas" e que elas poderiam rodar sem o gerente de projetos. Após seis meses os projetos no departamento pareciam como os demais departamentos da organização - atrasados, com bugs e sendo continuamente corrigidos.

Você não tem que entender toda a mágica que faz seu projeto funcionar mas não te machuca saber parte dela - ou apreciar alguém que entende as partes que você não entende.

Mais importante. certifique-se que quando a mágica parar ela possa ser reiniciada.

Por [AlanGriffiths](http://programmer.97things.oreilly.com/wiki/index.php/AlanGriffiths)