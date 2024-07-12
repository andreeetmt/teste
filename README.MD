<h1 align="center"> Jogo da Idosa👵🎮 </h1>

## Introdução
Este é um código feito na linguagem C++ para representar um clássico jogo da velha, apelidado carinhosamente de Jogo da Idosa pelos criadores. O jogo pode ser jogado por 2 jogadores, no clássico estilo PVP (jogador contra jogador). Também pode ser jogado no modo PVE (jogador contra o computador). O código está organizado de forma a ser claro e fácil de entender, com funções separadas para cada parte do jogo.

## Membros do Grupo
- André Luís Furtado Cabral (241024590)
- André Monteiro Toussaint (241038058)
- Arthur Morais de Brito Simões Ferreira (241024482)
- Bernardo de Alencar Monteiro (241008460)
- Guilherme Toledo Osanai Lima (241008498)
- Gustavo Neri Alves Almeida (241008569)

## :hammer: Inclusão de Bibliotecas
- `#include <iostream>` - Biblioteca base do C++
- `#include <vector>` - Biblioteca para facilitar a manipulação de vetores
- `#include <random>` - Biblioteca para usar o random
- `#include <unistd.h>` - Biblioteca para usar a função sleep()

## Funções

### Limpar Tela
```cpp
void LimparTela() {
#ifdef _WIN32
    system("cls");  
#else
    system("clear");  
#endif
}
```
Função para limpar a tela em diferentes sistemas operacionais.
### Gerador de Números
```cpp

random_device rd; 
mt19937 gen(rd()); 
uniform_int_distribution<> dist(0, 8); 

```
Funçao para o computador gerar numeros e assim decidir suas jogadas.

###  Declaraçao de varivaveis
```cpp

vector<string> tabuleiro(9, " "); 
string situacao;
bool jogadores = true, velha;
string Jogador1 = "X"; 
string Jogador2 = "O"; 
int contadorX1 = 0, contadorO1 = 0, contadorX2 = 0, contadorO2 = 0; 

```
Declaração de variáveis globais usadas no jogo, incluindo o tabuleiro, status dos jogadores e contadores de vitórias.

###  Tabuleiro
```cpp

void TabuleiroNovo() {
    tabuleiro.clear();
    tabuleiro.resize(9, " ");
}
```
Inicia um tabuleiro clássico de jogo da velha.


###  Tabuleiro Por Jogada
```cpp

void Tabuleiro() {
    cout << "Tabuleiro:\n";
    cout << " " << tabuleiro[0] << " | " << tabuleiro[1] << " | " << tabuleiro[2] << "           1 | 2 | 3 \n";
    cout << "---+---+---          ---+---+---\n";
    cout << " " << tabuleiro[3] << " | " << tabuleiro[4] << " | " << tabuleiro[5] << "           4 | 5 | 6 \n";
    cout << "---+---+---          ---+---+---\n";
    cout << " " << tabuleiro[6] << " | " << tabuleiro[7] << " | " << tabuleiro[8] << "           7 | 8 | 9 \n";
}

```

Exibe o tabuleiro atual do jogo, atualizando após cada rodada.

### Função Casa Ocupada
```cpp
bool CasaOcupada(int posicao) {
    return tabuleiro[posicao - 1] != " ";
}
```
Verifica se uma posiçao no tabuleiro está ocupada.


