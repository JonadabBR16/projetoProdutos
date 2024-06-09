#include <stdio.h>
#define MAX_PRODUCTS 100

int carrinho[MAX_PRODUCTS];
int num_produtos = 0;

void adicionar_produto(int produto) {
    if (num_produtos < MAX_PRODUCTS) {
        carrinho[num_produtos] = produto;
        num_produtos++;
        printf("Produto %d adicionado.\n", produto);
    } else {
        printf("Não e possivel adicionar mais produtos.\n");
    }
}

void remover_produto() {
    if (num_produtos > 0) {
        int produto = carrinho[num_produtos - 1];
        num_produtos--;
        printf("Produto %d removido do carrinho.\n", produto);
    } else {
        printf("Carrinho vazio! Não há produtos para remover.\n");
    }
}

int main() {
    int opcao;
    int produto;

     while(1) {
        printf("\n\t º---------------------------º");
        printf("\n\t |          MENU             |");
        printf("\n\t |---------------------------|");
        printf("\n\t | [1] - ADICIONAR PRODUTOS! |");
        printf("\n\t | [2] - COMPRAR PRODUTOS!   |");
        printf("\n\t | [3] - SAIR DO CODIGO!     |");
        printf("\n\t º---------------------------º");

        switch (opcao) {
            case 1:
                printf("Qual Produto Quer Adicinar?: ");
                scanf("%d", &produto);
                adicionar_produto(produto);
                break;
            case 2:
                remover_produto();
                break;
            case 3:
                printf("Saindo...\n");
                return 0;
            default:
                printf("Opção invalida! Tente novamente.\n");
                break;
        }
    }

    return 0;
}
