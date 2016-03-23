``` c
#include <stdio.h>
#include <stdlib.h>

#define TAMANHO 100
#define TAMANHO_TREINO 30

void push(Pilha*,int);
int pop(Pilha*);
void show(Pilha*);
void copyStack(Pilha*, Pilha*);
void pushTreino(PilhaTreino*,Treino);

typedef struct {
    int  item[TAMANHO];
    unsigned int position;
} Pilha ;


typedef struct {
    int     dia;
    int     peito;
    int     livre;
} Treino ;

typedef struct {
    Treino  item[TAMANHO_TREINO];
    unsigned int position;
} PilhaTreino ;

PilhaTreino* pilhaTreino;

int i = 1;

Pilha* pilha;
Pilha* pilha2;
Pilha* pilha3;

int tmp=0;
int main()
{
    pilhaTreino = malloc(sizeof(PilhaTreino));
    pilhaTreino->position = 0;
    pilha = malloc(sizeof(Pilha));
    pilha->position = 0;
    pilha2 = malloc(sizeof(Pilha));
    pilha2->position = 0;
    pilha3 = malloc(sizeof(Pilha));
    pilha3->position = 0;

    // Resposta 1
    push(pilha,5);
    push(pilha,3);
    pop(pilha);
    push(pilha,2);
    push(pilha,8);
    pop(pilha);
    pop(pilha);
    push(pilha,9);
    push(pilha,1);
    pop(pilha);
    push(pilha,7);
    push(pilha,6);
    pop(pilha);
    pop(pilha);
    push(pilha,4);
    pop(pilha);
    pop(pilha);
    // Fim Resposta 1

    // Resposta 2 esta nas funcoes

    // Resposta 3
    for(i=0;i<100;i++){
        if(i%2 == 0){ // Adiciona somente os pares
            push(pilha, i);
        }
    }
    // Fim Resposta 3

    // Resposta 4
    push(pilha,5);
    push(pilha,6);
    push(pilha,8);
    printf("\nPilha1\n");
    show(pilha);
    copyStack(pilha2, pilha);
    printf("\nCopia de dados\n");

    for(i=0;i<3;i++){
        printf("%i + %i = %i\n",pilha2->item[i],pilha->item[i],pilha2->item[i]+pilha->item[i]);
        push(pilha3,pilha2->item[i]+pilha->item[i]);
    }

    printf("\nPilha2\n");
    show(pilha2);
    printf("\nPilha Soma\n");
    show(pilha3);
    // Fim resposta 4

    // Resposta 5
    Treino treino;
    for(i=0;i<30;i++){
        treino.livre=600+i*200;
        treino.dia=1+i;
        treino.peito=200+i*150;
        pushTreino(pilhaTreino,treino);
    }
    return 0;
}

void copyStack(Pilha *_destino, Pilha *_origem)
{
    printf("Tamanho da pilha de origem [%i]\n\n",_origem->position);
    int size = _origem->position;
    for(i=0;i<size;i++)
        push(_destino, pop(_origem));
}

void show(Pilha *_pilha){
    printf("Tamanho total %i.\nTamanho Ocupado %i\nDados da Pilha\n", TAMANHO, _pilha->position);
    for(i = 0; i<_pilha->position;i++){
        printf("%i->%4d\n",i,_pilha->item[i]);
    }
}

int pop(Pilha* _pilha){
    if((_pilha->position)==0)
        {
            printf("Error: Stack Underflow.\n");
            exit(1);
        }
    int retorno = _pilha->item[--_pilha->position];
    printf("<-[%1i]%8i\n", _pilha->position, retorno);
    return retorno;
}

int pushTreino(PilhaTreino* _pilha, Treino n)
{
    if(_pilha->position == TAMANHO)
        {
            printf("Error: Stack Overflow.\n");
            return 0;
        }

    _pilha->item[_pilha->position++] = n;
    printf("->[%1i]\n", _pilha->position-1, n.dia);
    printf("    |->Dia    %5i\n",  n.dia);
    printf("    |->Livre  %5i\n",  n.livre);
    printf("    |->Peito  %5i\n",  n.peito);
    return 1;
}

int push(Pilha* _pilha, int n)
{
    if(_pilha->position == TAMANHO)
        {
            printf("Error: Stack Overflow.\n");
            return 0;
        }
    _pilha->item[_pilha->position++] = n;
    printf("->[%1i]%8i\n", _pilha->position-1, n);
    return 1;
}
```
