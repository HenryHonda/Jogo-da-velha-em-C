#include <stdio.h>
#include <stdlib.h>

void zeraMatriz();
void mostraMatriz();
void jogaVoce();
char verificaFim();
void jogaComputI();

char Matriz[3][3]; //Variavel Global

main()
{
    char ok;
    int vez = 0; //1=Você, 2=Computador
    printf("Jogo da velha\n");
    ok = ' ';
    while (vez != 1 && vez != 2)
    {
        printf("Joga primeiro - 1 = Voce (X), 2 = Computador (O): ");
        scanf("%d", &vez);
    }
    zeraMatriz();

    do
    {
        if (vez == 1)
        {
            jogaVoce();
            ok = verificaFim();
            if (ok != ' ')
                break; //Existe vencedor ou empatou
            vez = 2;
        }
        if (vez == 2)
        {
            jogaComputI();
            ok = verificaFim();
            if (ok != ' ')
                break;
            vez = 1;
        }
        mostraMatriz();

    } while (ok == ' ');

    printf("==========================\n");
    mostraMatriz();
    if (ok == 'X')
        printf("Parabens, você ganhou!\n");
    else if (ok == 'O')
        printf("Sinto muito, o computador ganhou...\n");
    else
        printf("Empate\n");
    printf("==========================\n");
}

void zeraMatriz() //Função sem argumento porque Matriz é variavel GLOBAL
{
    int i, j;
    for (i = 0; i < 3; i++)
        for (j = 0; j < 3; j++)
            Matriz[i][j] = ' ';
}

void mostraMatriz()
{
    int t;
    for (t = 0; t < 3; t++)
    {
        printf("  %c  |  %c  |  %c  ", Matriz[t][0], Matriz[t][1], Matriz[t][2]);
        if (t != 2)
            printf("\n-----|-----|-----\n");
    }
    printf("\n");
}

void jogaVoce()
{
    int x, y;
    printf("Digite as coordenadas (separadas por espaço): ");
    scanf("%d %d", &x, &y);
    x--;
    y--;
    if (Matriz[x][y] != ' ')
    {
        printf("Posição invalida, digite novamente!\n");
        jogaVoce();
    }
    else
        Matriz[x][y] = 'X';
}

void jogaComputI()
{
    int t;
    //Veifica coluna
    for (t = 0; t < 3; t++)
    {
        if (Matriz[t][0] == 'O' && Matriz[t][1] == 'O' && Matriz[t][2] == ' ')
        {
            Matriz[t][2] = 'O';
            return;
        }
        if (Matriz[t][0] == 'O' && Matriz[t][1] == ' ' && Matriz[t][2] == 'O')
        {
            Matriz[t][1] = 'O';
            return;
        }
        if (Matriz[t][0] == ' ' && Matriz[t][1] == 'O' && Matriz[t][2] == 'O')
        {
            Matriz[t][0] = 'O';
            return;
        }
    }
    //Veifica outra coluna
    for (t = 0; t < 3; t++)
    {
        if (Matriz[0][t] == 'O' && Matriz[1][t] == 'O' && Matriz[2][t] == ' ')
        {
            Matriz[2][t] = 'O';
            return;
        }
        if (Matriz[0][t] == 'O' && Matriz[1][t] == ' ' && Matriz[2][t] == 'O')
        {
            Matriz[1][t] = 'O';
            return;
        }
        if (Matriz[0][t] == ' ' && Matriz[1][t] == 'O' && Matriz[2][t] == 'O')
        {
            Matriz[0][t] = 'O';
            return;
        }
    }

    //Verifica diagonal
    if (Matriz[0][2] == 'O' && Matriz[1][1] == 'O' && Matriz[2][1] == ' ')
    {
        Matriz[2][1] = 'O';
        return;
    }
    if (Matriz[0][2] == 'O' && Matriz[1][1] == ' ' && Matriz[2][1] == 'O')
    {
        Matriz[1][1] = 'O';
        return;
    }
    if (Matriz[0][2] == ' ' && Matriz[1][1] == 'O' && Matriz[2][1] == 'O')
    {
        Matriz[0][2] = 'O';
        return;
    }

    //Verifica  OUTRA diagonal
    if (Matriz[0][0] == 'O' && Matriz[1][1] == 'O' && Matriz[2][2] == ' ')
    {
        Matriz[2][2] = 'O';
        return;
    }
    if (Matriz[0][0] == 'O' && Matriz[1][1] == ' ' && Matriz[2][2] == 'O')
    {
        Matriz[1][1] = 'O';
        return;
    }
    if (Matriz[0][0] == ' ' && Matriz[1][1] == 'O' && Matriz[2][2] == 'O')
    {
        Matriz[0][0] = 'O';
        return;
    }

    for (t = 0; t < 3; t++)
    {
        if (Matriz[t][0] == 'X' && Matriz[t][1] == 'X' && Matriz[t][2] == ' ')
        {
            Matriz[t][2] = 'O';
            return;
        }
        if (Matriz[t][0] == 'X' && Matriz[t][1] == ' ' && Matriz[t][2] == 'X')
        {
            Matriz[t][1] = 'O';
            return;
        }
        if (Matriz[t][0] == ' ' && Matriz[t][1] == 'X' && Matriz[t][2] == 'X')
        {
            Matriz[t][0] = 'O';
            return;
        }
    }
    for (t = 0; t < 3; t++)
    {
        if (Matriz[0][t] == 'X' && Matriz[1][t] == 'X' && Matriz[2][t] == ' ')
        {
            Matriz[2][t] = 'O';
            return;
        }
        if (Matriz[0][t] == 'X' && Matriz[1][t] == ' ' && Matriz[2][t] == 'X')
        {
            Matriz[1][t] = 'O';
            return;
        }
        if (Matriz[0][t] == ' ' && Matriz[1][t] == 'X' && Matriz[2][t] == 'X')
        {
            Matriz[0][t] = 'O';
            return;
        }
    }
    //VERIFICA DIAGONAL
    if (Matriz[0][0] == 'X' && Matriz[1][1] == 'X' && Matriz[2][2] == ' ')
    {
        Matriz[2][2] = 'O';
        return;
    }

    if (Matriz[0][0] == 'X' && Matriz[1][1] == ' ' && Matriz[2][2] == 'X')
    {
        Matriz[1][1] = 'O';
        return;
    }
    if (Matriz[0][0] == ' ' && Matriz[1][1] == 'X' && Matriz[2][2] == 'X')
    {
        Matriz[0][0] = 'O';
        return;
    }
    //Verifica outra diagonal
    if (Matriz[0][2] == 'X' && Matriz[1][1] == 'X' && Matriz[2][0] == ' ')
    {
        Matriz[2][0] = 'O';
        return;
    }

    if (Matriz[0][2] == 'X' && Matriz[1][1] == ' ' && Matriz[2][0] == 'X')
    {
        Matriz[1][1] = 'O';
        return;
    }
    if (Matriz[0][2] == ' ' && Matriz[1][1] == 'X' && Matriz[2][0] == 'X')
    {
        Matriz[0][0] = 'O';
        return;
    }

    int i, j;
    for (i = 0; i < 3; i++)
    {
        for (j = 0; j < 3; j++)
            if (Matriz[i][j] == ' ')
                break;
        if (Matriz[i][j] == ' ')
            break;
    }
    if (i == 3 && j == 3)
        return 'e';
    Matriz[i][j] = 'O';
}

char verificaFim()
{
    int t;
    for (t = 0; t < 3; t++)
        if (Matriz[t][0] == Matriz[t][1] &&
            Matriz[t][0] == Matriz[t][2])
            return Matriz[t][0];

    for (t = 0; t < 3; t++)
        if (Matriz[0][t] == Matriz[1][t] &&
            Matriz[0][t] == Matriz[2][t])
            return Matriz[0][t];

    for (t = 0; t < 3; t++)
        if (Matriz[0][0] == Matriz[1][1] &&
            Matriz[0][0] == Matriz[1][2])
            return Matriz[0][0];

    for (t = 0; t < 3; t++)
        if (Matriz[0][2] == Matriz[1][1] &&
            Matriz[0][2] == Matriz[2][0])
            return Matriz[0][2];

    int i, j;
    t = -1;
    for (i = 0; i < 3; i++)
        for (j = 0; j < 3; j++)
            if (Matriz[i][j] == ' ')
            {
                t = 0;
                break;
            }
    if (t == -1)
        return 'e';
    return ' ';
}
