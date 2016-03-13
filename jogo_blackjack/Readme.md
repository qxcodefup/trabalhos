# Blackjack 21, Um jogo de cartas inocente

**Equipe QXCODE**
* David Sena
    * sena.ufc@gmail.com
* Ronildo Oliveira 
    * ro.nildooliveira@hotmail.com

## Instruções Gerais

O objetivo desse trabalho é simular o jogo de **Blackjack 21** entre um
usuário e a mesa. As opções do jogador são simplificadas em relação ao
jogo original.

![Ganhou](./latex/imagens/blackjack)

<http://pt.blackjack.org/regras/>

<http://pt.wikipedia.org/wiki/Blackjack>

Você pode jogar online uma simulação bem parecida com a que vamos
implementar para compreender as regras.

<http://jogosonline.uol.com.br/blackjack-gentleman-s-bet_43651.html>

## Regras Básicas

O objetivo do jogo é ter a maior pontuação de cartas, desque não estoure o valor
máximo de 21 pontos. Quem tiver mais pontos ganha, se alguém passar de 21 perde.

Todas as cartas com 10 ou menos [2, 3, 4, 5, 6, 7 ,8, 9, 10] têm um
valor igual a seu número. Os naipes não influenciam o valor das cartas.
O quatro de paus possui o mesmo valor que o quatro de ouros. 

Se um jogador receber as seguintes cartas: [2, 5 ,8], o valor de
sua mão equivalerá a 15.

Os _Valetes, Damas e Reis_, [J, Q, K] são todos equivalentes a **10**. 
Tal como as cartas numeradas, naipes diferentes não afetam o valor dessas cartas. 

Se um jogador receber [K, Q] como suas duas primeiras cartas viradas para cima, 
elas possuem soma 20, a segunda pontuação mais alta, abaixo perdendo pro 21.

A última carta, o _Ás_ [A], tem um valor especial no jogo de **Blackjack**. O
[A] pode valer **1** ou **11**. O que for mais vantajoso para a mão do jogador. 

Um [K, 8, A] vale 19 pontos, pois se o [A] valesse 11 em sua mão, o jogador
teria feito 29 pontos e perdido. Com o [A] valendo 1 ele fez 19 pontos. 

O algoritmo é bem simples. 

    Conte a quantidade de [A]s da mão. 
    Pense-os como valendo 11. 
    Enquanto a soma for maior que 21 e houver [A]s na mão
        Faça um [A] valer 1.
        Retire um [A] da contagem.

## Implementação

Opções do usuário : Pedir Carta (Hit) ou Parar.

O jogador inicia com 2 cartas e a mesa com 1 carta.

O jogador pode pedir quantas cartas quiser até parar ou estourar o valor
de 21.

Se o jogador parar sem estourar, a mesa vai jogar até vencer o jogador
ou estourar. Se a mesa tiver a mesma quantidade de pontos do jogador ela
para e vence.

Nos trechos que representam a saída do terminal, os símbolos `>>`
representam que o programa para e espera a entrada do usuário.

## Exemplo

Uma única rodada, um jogador e a mesa. A cada rodada o programa pergunta
se o jogador quer para ou continuar. Se quiser continuar, recebe uma
carta aleatória. Abaixo, um exemplo de saída.

    Iniciando Rodada:
    # Mesa recebe  7 - Total  7 [ 7 ]
    # Voce recebe  A - Total 11 [ A ]
    # Voce recebe  2 - Total 13 [ A 2 ]
    Pedir = 1, Parar = 2 
    >> 1

    # Voce recebe  3 - Total 16 [ A 2 3 ]
    Pedir = 1, Parar = 2 
    >> 2

    # Mesa recebe  2 - Total  9 [ 7 2 ]
    # Mesa recebe  7 - Total 16 [ 7 2 7 ]
    # Mesa (16), Voce (16)
    Voce perdeu!

Nova execução do programa.

    Iniciando Rodada:
    # Mesa recebe  7 - Total  7 [ 7 ]
    # Voce recebe  A - Total 11 [ A ]
    # Voce recebe  2 - Total 13 [ A 2 ]
    Pedir = 1, Parar = 2 
    >> 1

    # Voce recebe  Q - Total 13 [ A 2 Q ]
    Pedir = 1, Parar = 2 
    >> 1

    # Voce recebe  5 - Total 18 [ A 2 Q 5 ]
    Pedir = 1, Parar = 2 
    >> 2

    # Mesa recebe  8 - Total 15 [ 7 8 ]
    # Mesa recebe  7 - Total 22 [ 7 8 7 ]

    # Mesa (22), Voce (18)
    Voce Ganhou

## Melhorias

-   Você pode colocar um sistema de apostas, onde o jogador começa com
    uma certa quantidade de dinheiro e pode ganhar ou perder dinheiro.

-   Você pode manter o jogador jogando enquanto ele quiser ou tiver
    dinheiro.

-   Se você ainda quer um desafio, que tal implementar um jogo para
    múltiplos jogadores? Pesquise um pouco sobre as regras para
    múltiplos jogadores.

-   Uma outra possibilidade é adicionar as regras adicionais como dobrar
    ou partir as cartas.

**Bom Trabalho**.

