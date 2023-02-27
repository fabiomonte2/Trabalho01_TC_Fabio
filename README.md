# Trabalho01_TC_Fabio
Solu ̧c ̃ao 1
O comando abre o arquivo do pr ́oprio c ́odigo-fonte em modo de leitura. O m ́etodo read(),
lˆe todo o conte ́udo do arquivo em uma string chamada code. O comando print(code +
code), imprime duas c ́opias da string code. Como code cont ́em o c ́odigo-fonte do programa,
isso resultar ́a em imprimir o pr ́oprio c ́odigo-fonte do programa duas vezes em seguida.
1 Solu ̧c ̃ao 2
1.1 (a)
Para demonstrar que o conjunto das linguagens decid ́ıveis  ́e um subconjunto pr ́oprio
do conjunto das linguagens reconhec ́ıveis, podemos utilizar o exemplo da linguagem das
palavras que s ̃ao pal ́ındromos, ou seja, palavras que podem ser lidas da mesma maneira
de tr ́as para frente e de frente para tr ́as.
Essa linguagem  ́e reconhec ́ıvel, pois podemos construir uma m ́aquina de Turing que lˆe
a entrada da esquerda para a direita e da direita para a esquerda ao mesmo tempo, e se
as duas leituras se encontram no meio da palavra, a m ́aquina reconhece a entrada como
um pal ́ındromo. No entanto, essa linguagem n ̃ao  ́e decid ́ıvel, pois n ̃ao  ́e poss ́ıvel construir
uma m ́aquina de Turing que pare em um n ́umero finito de passos para todas as entradas
poss ́ıveis e decida se uma palavra  ́e um pal ́ındromo ou n ̃ao.
Essa fun ̧c ̃ao utiliza a t ́ecnica de percorrer a palavra da esquerda para a direita e da
direita para a esquerda ao mesmo tempo, verificando se as letras em cada posi ̧c ̃ao cor-
respondente s ̃ao iguais. Se todas as letras forem iguais, a fun ̧c ̃ao retorna True, indicando
que a palavra  ́e um pal ́ındromo; caso contr ́ario, a fun ̧c ̃ao retorna False.
No entanto, para implementar uma m ́aquina de Turing que decida se uma palavra  ́e
um pal ́ındromo ou n ̃ao, seria necess ́ario que a m ́aquina parasse em um n ́umero finito
1
de passos para todas as palavras poss ́ıveis. Isso n ̃ao  ́e poss ́ıvel, pois para uma palavra
grande o suficiente, a m ́aquina precisaria percorrer toda a palavra at ́e o final para verificar
se  ́e um pal ́ındromo ou n ̃ao. Portanto, conclu ́ımos que a linguagem dos pal ́ındromos  ́e
reconhec ́ıvel, mas n ̃ao  ́e decid ́ıvel.
1.2 (b)
Para provar que HALT n ̃ao  ́e reconhec ́ıvel, utilizaremos o m ́etodo da diagonaliza ̧c ̃ao de
Cantor. Esse m ́etodo  ́e uma t ́ecnica de prova usada na teoria da computa ̧c ̃ao para mostrar
que certas linguagens n ̃ao s ̃ao decid ́ıveis ou n ̃ao s ̃ao reconhec ́ıveis.
Assumimos por contradi ̧c ̃ao que HALT  ́e reconhec ́ıvel por uma m ́aquina de Turing.
Isso significa que existe uma m ́aquina de Turing M que, quando recebe como entrada
a codifica ̧c ̃ao de outra m ́aquina de Turing, decide se essa m ́aquina p ́ara para todas as
entradas.
Vamos agora construir uma nova m ́aquina de Turing N que leva como entrada uma
string w e faz o seguinte:
Ignora a entrada w. Codifica a pr ́opria descri ̧c ̃ao da m ́aquina N em uma string x. Roda
a m ́aquina M com a entrada x. Se M aceita x, ent ̃ao N entra em um loop infinito. Caso
contr ́ario, N para imediatamente.
Quando rodamos a m ́aquina N com a entrada x. Se N p ́ara, ent ̃ao M aceitou x, o que
significa que a pr ́opria m ́aquina N n ̃ao para quando recebe como entrada a pr ́opria des-
cri ̧c ̃ao. Isso contradiz a suposi ̧c ̃ao de que M reconhece a linguagem HALT. Por outro lado,
se N entra em um loop infinito, ent ̃ao M rejeitou x, o que significa que a pr ́opria m ́aquina
N para quando recebe como entrada a pr ́opria descri ̧c ̃ao. Novamente, isso contradiz a
suposi ̧c ̃ao de que M reconhece a linguagem HALT.
Portanto, conclu ́ımos que n ̃ao  ́e poss ́ıvel construir uma m ́aquina de Turing que reco-
nhe ̧ca a linguagem HALT.
Observou-se que, para executar esse c ́odigo,  ́e necess ́ario implementar uma fun ̧c ̃ao M
que decide se uma m ́aquina de Turing p ́ara para todas as entradas, o que n ̃ao  ́e poss ́ıvel
de acordo com o nosso resultado acima.
2 Solu ̧c ̃ao 3
O Problema de Correspondˆencia de Post (PCP) consiste em determinar se  ́e poss ́ıvel
formar uma sequˆencia de pe ̧cas de domin ́o de um conjunto finito, de forma que a conca-
tena ̧c ̃ao das strings da parte de cima seja igual `a concatena ̧c ̃ao das strings da parte de
baixo.
O Problema de Correspondˆencia de Post bobo (SPCP)  ́e uma varia ̧c ̃ao do PCP, com a
restri ̧c ̃ao adicional de que as strings da parte de cima e da parte de baixo de cada pe ̧ca
de domin ́o devem ter o mesmo tamanho.
Para mostrar que o SPCP  ́e decid ́ıvel, podemos construir uma m ́aquina de Turing que,
dada uma instˆancia do problema, verifica se  ́e poss ́ıvel formar uma sequˆencia de pe ̧cas
de domin ́o que satisfa ̧ca a condi ̧c ̃ao de igualdade entre as strings da parte de cima e da
parte de baixo de cada pe ̧ca.
2
A ideia principal  ́e testar todas as poss ́ıveis sequˆencias de pe ̧cas de domin ́o de com-
primento limitado, de forma sistem ́atica, at ́e encontrar uma sequˆencia que satisfa ̧ca a
condi ̧c ̃ao de igualdade.
A fun ̧c ̃ao spcp recebe como argumento uma lista de tuplas representando os domin ́os,
em que cada tupla cont ́em as strings da parte de cima e da parte de baixo do domin ́o. A
fun ̧c ̃ao primeiro verifica se todos os domin ́os tˆem o mesmo tamanho e, em seguida, testa
todas as poss ́ıveis sequˆencias de domin ́os utilizando a fun ̧c ̃ao itertools.product. Para
cada sequˆencia de domin ́os, a fun ̧c ̃ao concatena as strings da parte de cima e da parte de
baixo de cada domin ́o e verifica se s ̃ao iguais. Se encontrar uma sequˆencia que satisfa ̧ca
a condi ̧c ̃ao, a fun ̧c ̃ao retorna True. Caso contr ́ario, a fun ̧c ̃ao retorna False.
Como a fun ̧c ̃ao testa todas as poss ́ıveis sequˆencias de domin ́os de comprimento limitado,
ela eventualmente encontrar ́a uma sequˆencia que satisfa ̧ca a condi ̧c ̃ao, se tal sequˆencia
existir. Portanto, conclu ́ımos que o SPCP  ́e decid ́ıvel.
3 Solu ̧c ̃ao 4
Explica ̧c ̃ao da prova:
Primeiramente, criamos as express ̃oes lambda ”zero”e ”um”que correspondem `as fun ̧c ̃oes
identidade para os valores 0 e 1, respectivamente. Em seguida, criamos a express ̃ao
lambda ”ALT”de acordo com a defini ̧c ̃ao dada, que recebe trˆes parˆametros a, b e c e
retorna o resultado da aplica ̧c ̃ao da f ́ormula dada. Para provar que a express ̃ao lambda
”ALT”computa a fun ̧c ̃ao ”pelo menos dois”, fazemos um teste para todas as combina ̧c ̃oes
poss ́ıveis de valores 0 e 1 para a, b e c. Para cada combina ̧c ̃ao, aplicamos a express ̃ao
”ALT”aos valores correspondentes de a, b e c e contamos quantos resultados iguais a 1
s ̃ao obtidos. Se o n ́umero de resultados iguais a 1 for maior ou igual a 2, ent ̃ao a fun ̧c ̃ao
”pelo menos dois”deve retornar 1 (ou seja, a express ̃ao ”ALT”deve retornar ”um”). Caso
contr ́ario, a fun ̧c ̃ao deve retornar 0 (ou seja, a express ̃ao ”ALT”deve retornar ”zero”).
Para verificar se a express ̃ao ”ALT”est ́a correta, comparamos o resultado obtido com
o valor esperado (0 ou 1) e usamos a fun ̧c ̃ao assert para garantir que o resultado  ́e o
esperado.
4 Solu ̧c ̃ao 5
Para implementar as fun ̧c ̃oes MIN, MAX, APPEND e REVERSE em c ́alculo lambda
usando a codifica ̧c ̃ao de Church, precisamos definir as representa ̧c ̃oes de booleanos, n ́umeros
naturais, pares e listas em termos de fun ̧c ̃oes lambda.
Representa ̧c ̃ao de Booleanos:
Utilizaremos a representa ̧c ̃ao de booleanos de Church, em que um booleano  ́e uma
fun ̧c ̃ao que recebe dois argumentos e retorna o primeiro argumento se for verdadeiro e o
segundo argumento se for falso.
true = x.y.x
false = x.y.y
Representa ̧c ̃ao de N ́umeros Naturais:
3
Utilizaremos a representa ̧c ̃ao de n ́umeros naturais de Church, em que um n ́umero
natural  ́e uma fun ̧c ̃ao que recebe uma fun ̧c ̃ao e um valor inicial e aplica a fun ̧c ̃ao n vezes
ao valor inicial.
zero = f.x.x
um = f.x.f x
dois = f.x.f (f x)
Representa ̧c ̃ao de Pares:
Utilizaremos a representa ̧c ̃ao de pares de Church, em que um par  ́e uma fun ̧c ̃ao que
recebe duas fun ̧c ̃oes e retorna a aplica ̧c ̃ao da primeira fun ̧c ̃ao a um valor e da segunda
fun ̧c ̃ao a outro valor.
pair = x.y.f.f x y
Representa ̧c ̃ao de Listas:
Utilizaremos a representa ̧c ̃ao de listas de Church, em que uma lista  ́e uma fun ̧c ̃ao que
recebe duas fun ̧c ̃oes e um valor inicial e aplica a primeira fun ̧c ̃ao a cada elemento da lista,
iniciando com o valor inicial, e a segunda fun ̧c ̃ao a cada resultado parcial.
emptylist = f.x.x
cons = x.y.f.f x y
Agora podemos implementar as fun ̧c ̃oes MIN, MAX, APPEND e REVERSE em termos
dessas representa ̧c ̃oes.
4.1 (a)
MIN — recebe uma lista de n ́umeros e retorna o menor deles.
min = l.l (x.y.pair (a.b.((a ¡ b) true false) x y) x) (pair zero zero)
Explica ̧c ̃ao: A fun ̧c ̃ao lambda min recebe uma lista l de n ́umeros e usa a fun ̧c ̃ao de lista
l para percorrer a lista e encontrar o menor n ́umero, armazenando-o em um par com a
representa ̧c ̃ao do n ́umero zero. A cada elemento da lista l, a fun ̧c ̃ao lambda pair  ́e usada
para comparar o n ́umero atual com o n ́umero armazenado no par e armazenar o menor
dos dois no par. Finalmente, a primeira fun ̧c ̃ao do par resultante  ́e retornada como o
menor n ́umero.
4.2 (b)
MAX — recebe uma lista de n ́umeros e retorna o maior deles.
max = l.l (x.y.pair (a.b.((a ¿ b) true false) x y) x) (pair zero zero)
Explica ̧c ̃ao: A fun ̧c ̃ao lambda max recebe uma lista l de n ́umeros e usa a fun ̧c ̃ao de
lista l para percorrer a lista e encontrar o maior n ́umero, armazenando-o em um par com
a representa ̧c ̃ao do n ́umero zero. A cada elemento da lista l, a fun ̧c ̃ao lambda pair  ́e usada
para comparar o n ́umero atual com o n ́umero armazenado no par e armazenar o maior
dos dois no par. Finalmente, a primeira fun ̧c ̃ao do par resultante  ́e retornada como o
maior n ́umero.
4.3 (c)
APPEND — recebe duas listas e retorna a concatena ̧c ̃ao destas duas listas.
4
append = l1.l2.l1 cons l2
Explica ̧c ̃ao: A fun ̧c ̃ao lambda append recebe duas listas l1 e l2 e simplesmente as
concatena usando a fun ̧c ̃ao de lista cons.
4.4 (d)
REVERSE — recebe uma lista e retorna a lista invertida.
reverse = l.l (x.y.cons y x) emptylist
Explica ̧c ̃ao: A fun ̧c ̃ao lambda reverse recebe uma lista l e usa a fun ̧c ̃ao de lista l para
percorrer a lista e construir uma nova lista invertida. A cada elemento da lista l, a fun ̧c ̃ao
lambda cons  ́e usada para adicionar o elemento `a lista resultante, mas no in ́ıcio da lista
em vez do final. A lista resultante  ́e iniciada com a lista vazia usando a fun ̧c ̃ao emptylist.
5 Solu ̧c ̃ao 6
(a) e (b) As fun ̧c ̃oes lambda min e max s ̃ao definidas com a ajuda da fun ̧c ̃ao auxiliar
lambda l, que  ́e a fun ̧c ̃ao de lista em si. A fun ̧c ̃ao de lista lambda l percorre a lista l e
usa a fun ̧c ̃ao lambda pair para comparar o n ́umero atual com o n ́umero armazenado no
par e armazenar o menor ou maior dos dois no par. Finalmente, a primeira fun ̧c ̃ao do
par resultante  ́e retornada como o menor ou maior n ́umero, respectivamente.
(c) A fun ̧c ̃ao lambda append  ́e definida com a ajuda da fun ̧c ̃ao auxiliar lambda f,
que recebe duas listas e uma fun ̧c ̃ao e uma fun ̧c ̃ao auxiliar lambda k que retorna a
concatena ̧c ̃ao das duas listas. A fun ̧c ̃ao lambda append aplica a fun ̧c ̃ao lambda k a cada
elemento da primeira lista l1 e a cada elemento da segunda lista l2, concatenando-os.
(d) A fun ̧c ̃ao lambda reverse  ́e definida com a ajuda da fun ̧c ̃ao auxiliar lambda l, que
 ́e a fun ̧c ̃ao de lista em si. A fun ̧c ̃ao de lista lambda l percorre a lista l e usa a fun ̧c ̃ao
lambda cons para inverter a ordem dos elementos da lista. A lista invertida resultante  ́e
retornada.
