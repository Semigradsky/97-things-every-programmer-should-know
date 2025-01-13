# Não ignore aquele erro!

> *Eu estava pela rua certa noite para encontrar alguns amigos em um bar. Não tomávamos uma cerveja juntos há algum tempo e eu estava querendo vê-los novamente. Naquela correria, eu não estava olhando para o caminho. tropecei no meio-fio e caí de cara no chão. Bem, serviu para aprender a prestar atenção, eu assumo.*

> *Machucou minha perna mas eu estava atrasado para encontrar meus amigos. Então me levantei e segui o caminho. À medida que eu caminhava a dor estava ficando pior. Embora eu tivesse achado que era apenas um choque, rapidamente notei que havia algo de errado.*

> *Consegui checar no bar de qualquer forma. Já estava agonizando na hora que cheguei. Não tive uma boa noite, porque fui terrivelmente distraído. Na manhã seguinte, fui ao médico e descobri que quebrei o osso da canela. Caso tivesse parado quando senti a primeira dor, teria evitado muito dano adicional que eu causei ao seguir andando. Foi, provavelmente, a pior manhã do dia seguinte da minha vida.*

Muitos programadores escrevem código da mesma forma que minha noite desastrada.

*Erro, que erro? Não deve ser sério. Honestamente. Posso ignorá-lo.* Essa não é uma estratégia vencedora para código robusto. No ato, isso é apenas preguiça. (O tipo errado de preguiça). Não importa quão improvável você pense que exista um erro no seu código, você deve sempre procurar por ele e sempre tratá-lo. Toda vez. Você não está economizando tempo se não fizer isso: você está armazenando problemas potenciais para o futuro.

Nós relatamos erros em nosso código em um certo número de formas, incluindo:

- **Códigos de retorno** podem ser usados como o valor resultante da função para indicar que "não funcionou." Códigos de erro são muito fáceis de ignorar. Você não verá nada no código para realçar o problema. Adicionalmente, tornou-se prática padrão ignorar alguns valores de retorno de funções padrão na linguagem C. Quão frequentemente você confere o valor de retorno da função printf?
- **errno** é uma aberração curiosa de C, uma variável global separada destinada a sinalizar um erro. É fácil de ignorar, difícil de usar, e leva a toda sorte de problemas indesejáveis - por exemplo, o que acontece quando múltiplas threads chamam a mesma função? Algumas plataformas isolam você da dor aqui; outras não.

- **Exceções** são uma forma mais estruturada, suportada pelas linguagens de programação, de sinalizar e manipular erros. E você não pode ignorá-las. Ou pode? Já vi muito código como esse:

```
try {
    // ...do something...
}
catch (...) {} // ignore errors
```

A lição dessa construção horrível é que ela ressalta o fato que você está fazendo algo moralmente duvidoso.

E você ignora um erro, fecha os olhos para ele, e finge que nada está errado, você está correndo grandes riscos. Da mesma forma que minha perna acabou em um estado pior do que seria caso tivesse parado de andar imediatamente, seguir em frente ignorando os erros de código pode levar a falhas muito complexas. Lide com os problemas na primeira oportunidade. Mantenha-os sob controle.
Não tratar adequadamente os erros conduz a:

- **Código frágil.** Código que está cheio de bugs difíceis de encontrar.
- **Código inseguro.** Hackers geralmente exploram tratamento de erro inadequado para invadir sistemas de software.
- **Estrutura pobre.** Se existem erros no seu código que são tediosos de lidar, você provavelmente tem uma interface pobre. Expresse-se melhor de forma que os erros sejam menos intrusivos e seu tratamento seja menos custoso.

Da mesma forma que você deve checar todos os erros em potencial no seu código, você precisa expor todas as condições potencialmente errôneas nas suas interfaces. Não as esconda, fingindo que seus serviços irão sempre funcionar.

Porque você não checa os erros? Existe um número de desculpas comuns. Quais dessas você concorda? Como resolver cada uma delas?

- Tratamento de erro polui o fluxo do código, tornando-o mais difícil de ler e mais complicado de entender o fluxo normal de execução.
- É trabalho extra e eu tenho um prazo apertado.
- Sei que essa chamada de função *nunca* retornará um erro (printf sempre funciona, malloc sempre retorna nova memória - se eles falharem teremos problemas ainda maiores...) .
- É somente uma prova de conceito e não precisa ser reescrito para implementação em produção.

Por [Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe)
