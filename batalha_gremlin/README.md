
Batalha Gremlin
===============

Esse arquivo define as regras da arena Gremlin. A arena Gremlin é uma simulação de um combate entre Gremlins. Pode ser implementado em vários níveis.


Fase 1: Nível Aprendiz.
=======================
Início do jogo:

* O jogo começa com 10 Gremlins.
* Todos devem ser aleatoriamente iniciados com atributos variados. 
* Cada Gremlin só tem os atributos char id, int forca e int vida.
* Em uma rodada todos os Gremlins atacam um por vez sequencialemente.
* Em seu turno, um Gremlin ataca aleatoriamente outro Gremlin do jogo que não ele mesmo. O atacado sempre revida atacando o agressor com METADE da sua força.

Quando o round termina:

* Se um Gremlin ficar com vida negativa ou zero, ele é removido da
      batalha.
* Outro round reinicia até que só sobre um vencedor.
* Se no último round os dois Gremlins morrerem, então não houve vencedor.
* Você deve mostrar o Gremlin vencedor se houver algum.

Fase 2: Nível Experiente.
=========================
Vamos criar algumas reviravoltas no nosso jogo.

* Os nomes dos Gremlins devem aleatórios e conter 4 letras. Deve iniciar com maiúsculo e as posições pares devem ser vogais. Ex: Cona, Bifu, Gori, Hijo.
* Um Gremlin tem dois novos atributos: revidar e raiva. 
* Revidar define quantas vezes ele pode revidar em um round. 
* Se um Gremlin é atacado e não puder revidar, ele aumenta sua força permanentemente. 
* O aumento da força é dado pelo seu atributo raiva. 
* Se o Gremlin atacado tiver ao menos 1 revidar, ele obrigatoriamente revida gastando 1 revidar. 
* A cada rodada revidar é reiniciado para o valor máximo.
* Execute a luta todos contra todos e mostre o vencedor se houver algum.

Fase 3: Nível Avançado.
=======================
Vamos criar dois times:

* Gremlins não lutam agora todos contra todos. Eles formam dois times de 4 Gremlins. Chamemos de times A e B. 
* Os Gremlins de um time atacam os Gremlins de outro time. O lado A começa atacando. 
* Alterne os Gremlins entre os lados A e B até que todos ataquem.
* As regras de revidar e raiva ainda são válidas. Porém agora, assim que a vida de um Gremlin fica negativa ele morre e sai do jogo, não apenas no fim do turno.

Fase 4: Nível Jedi.
===================
Aqui, vamos permitir que o jogador jogue contra a máquina.

Antes de começar o turno, cada Gremlin de ambos os times escolhe a ação que vai executar. Ao invés de apenas atacar, eles tem outras opções:

* **Meditar**: O Gremlin não ataca ninguém e ganha 20% da sua vida de volta nessa rodada, porém não pode recuperar mais que o máximo de sua vida original. Se ele for atacado enquanto se nessa rodada, não poderá revidar e não ganhará força extra por não revidar.
* **Defender**: O Gremlin entra em modo de defesa. Em modo de defesa ele serve de escudo para um Gremlin de seu time que ele escolher defender. Nenhum Gremlin do time adversário poderá atacar seu defendido nesse turno enquanto o defensor estiver vivo. O defensor ainda poderá revidar  normalmente.
*  **Absorver**: O Gremlin não ataca, mas se prepara para receber porrada. Se algum Gremlin do time adversário bater nele nessa rodada, ele sofrerá dano normalmente, mas também receberá o dobro da raiva na força.
* **Counter**: O defensor não não ataca, mas recebe metade do dano e revida com toda força.
* **Louco**: O Gremlin ataca com o dobro de sua força e não revidará nenhum ataque.


Fase 5: Nível Super Sayajin
===================

Que tal fazer alguma IA para a máquina ter alguma chance de ganhar o jogo?
