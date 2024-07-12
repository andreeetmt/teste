<h1 align="center"> Jogo da Idosa👵🎮 </h1>

## Introdução
Este é um código feito na linguagem c++ para representar um clássico jogo da velha, apelidado carinhosamente de Jogo da Idosa pelos criadores. O jogo pode
ser jogado por 2 jogadores, no clássico estilo estilo PVP, jogador contra jogador.Também pode ser jogado no modo PVE, jogador contra um computador. O código está organizado de forma a ser claro e fácil de entender, com funções separadas para cada parte do jogo.

## Membros do Grupo
- André Luís Furtado Cabral (241024590)
- André Monteiro Toussaint (241038058)
- Arthur Morais de Brito Simões Ferreira (241024482)
- Bernardo de Alencar Monteiro (241008460)
- Guilherme Toledo Osanai Lima (241008498)
- Gustavo Neri Alves Almeida (241008569)


# :hammer: Inclusão de Bibliotecas

- #include <iostream> - Biblioteca base do C++
- #include <vector> - Biblioteca para facilitar a manipulação de vetores
- #include <random> - Biblioteca para usar o random
-  #include <unistd.h> - Biblioteca para usar a função sleep()

# Funçoes
### Limpar Tela
```cpp
void LimparTela() {
#ifdef _WIN32
    system("cls");  
#else
    system("clear");  
#endif
}

Funçao para limpar a tela em diferentes sistemas operacionais.
###

### Gerador de numeros do computador
#random_device rd; // Gerador de números aleatórios baseado em hardware, se disponível
mt19937 gen(rd()); // Mersenne Twister 19937 como o gerador padrão
uniform_int_distribution<> dist(0, 8); // Números entre 0 e 8 (para um tabuleiro 3x3)

