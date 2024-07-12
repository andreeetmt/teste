h1 align="center"> Jogo da Idosa👵🎮 </h1>
Introdução

Este é um código feito na linguagem C++ para representar um clássico jogo da velha, apelidado carinhosamente de Jogo da Idosa pelos criadores. O jogo pode ser jogado por 2 jogadores, no clássico estilo PVP, jogador contra jogador. Também pode ser jogado no modo PVE, jogador contra um computador. O código está organizado de forma a ser claro e fácil de entender, com funções separadas para cada parte do jogo.
Membros do Grupo

    André Luís Furtado Cabral (241024590)
    André Monteiro Toussaint (241038058)
    Arthur Morais de Brito Simões Ferreira (241024482)
    Bernardo de Alencar Monteiro (241008460)
    Guilherme Toledo Osanai Lima (241008498)
    Gustavo Neri Alves Almeida (241008569)

Inclusão de Bibliotecas

cpp

#include <iostream> // Biblioteca base do C++
#include <vector> // Biblioteca para facilitar a manipulação de vetores
#include <random> // Biblioteca para usar o random
#include <unistd.h> // Biblioteca para usar a função sleep()

Funções
Limpar Tela

cpp

void LimparTela() {
#ifdef _WIN32
    system("cls");  
#else
    system("clear");  
#endif
}
// Função para limpar a tela em diferentes sistemas operacionais.

Gerador de Números do Computador

cpp

random_device rd; // Gerador de números aleatórios baseado em hardware, se disponível
mt19937 gen(rd()); // Mersenne Twister 19937 como o gerador padrão
uniform_int_distribution<> dist(0, 8); // Números entre 0 e 8 (para um tabuleiro 3x3)

Tabuleiro Novo

cpp

void TabuleiroNovo() {
    tabuleiro.clear();
    tabuleiro.resize(9, " ");
}
// Função para gerar um tabuleiro em branco.

Exibir Tabuleiro

cpp

void Tabuleiro() {
    cout << "Tabuleiro:\n";
    cout << " " << tabuleiro[0] << " | " << tabuleiro[1] << " | " << tabuleiro[2] << "           1 | 2 | 3 \n";
    cout << "---+---+---          ---+---+---\n";
    cout << " " << tabuleiro[3] << " | " << tabuleiro[4] << " | " << tabuleiro[5] << "           4 | 5 | 6 \n";
    cout << "---+---+---          ---+---+---\n";
    cout << " " << tabuleiro[6] << " | " << tabuleiro[7] << " | " << tabuleiro[8] << "           7 | 8 | 9 \n";
}
// Função para exibir o tabuleiro do jogo.

Checar se a Casa Está Ocupada

cpp

bool CasaOcupada(int posicao) {
    return tabuleiro[posicao - 1] != " ";
}
// Função para checar se a casa do tabuleiro está ocupada ou não.

Checar Vitória do Jogador X

cpp

bool vitoriaX() {
    if ((tabuleiro[0] == tabuleiro[1] && tabuleiro[1] == tabuleiro[2] && tabuleiro[0] == "X") ||
        (tabuleiro[3] == tabuleiro[4] && tabuleiro[4] == tabuleiro[5] && tabuleiro[3] == "X") ||
        (tabuleiro[6] == tabuleiro[7] && tabuleiro[7] == tabuleiro[8] && tabuleiro[6] == "X")) {
        return true
