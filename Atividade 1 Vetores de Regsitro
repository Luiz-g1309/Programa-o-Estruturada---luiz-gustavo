#include <stdio.h>
#include <string.h>

#define ESTADOS 26

typedef struct {
    char nome[30];
    int veiculos;
    int acidentes;
} Estado;

// (a) Procedimento para coletar dados
void coletarDados(Estado cad[]) {
    for (int i = 0; i < ESTADOS; i++) {
        printf("\nDigite o nome do estado %d: ", i + 1);
        scanf(" %[^\n]", cad[i].nome);
        printf("Numero de veiculos em 2007: ");
        scanf("%d", &cad[i].veiculos);
        printf("Numero de acidentes em 2007: ");
        scanf("%d", &cad[i].acidentes);
    }
}

// (b) Procedimento para achar maior e menor número de acidentes
void maiorMenorAcidentes(Estado cad[], int *iMaior, int *iMenor) {
    *iMaior = 0;
    *iMenor = 0;

    for (int i = 1; i < ESTADOS; i++) {
        if (cad[i].acidentes > cad[*iMaior].acidentes)
            *iMaior = i;
        if (cad[i].acidentes < cad[*iMenor].acidentes)
            *iMenor = i;
    }
}

// (c) Função para percentual de veículos envolvidos em acidentes
float percentualAcidentes(Estado e) {
    return (float)e.acidentes / e.veiculos * 100;
}

// (d) Função para média de acidentes no país
float mediaAcidentes(Estado cad[]) {
    int soma = 0;
    for (int i = 0; i < ESTADOS; i++)
        soma += cad[i].acidentes;
    return (float)soma / ESTADOS;
}

// (e) Procedimento para exibir estados acima da média
void acimaMedia(Estado cad[], float media) {
    printf("\n--- Estados com acidentes acima da media (%.2f) ---\n", media);
    for (int i = 0; i < ESTADOS; i++) {
        if (cad[i].acidentes > media)
            printf("%s - %d acidentes\n", cad[i].nome, cad[i].acidentes);
    }
}

int main() {
    Estado cadastro[ESTADOS];
    int iMaior, iMenor;
    float media;

    coletarDados(cadastro);
    maiorMenorAcidentes(cadastro, &iMaior, &iMenor);

    printf("\nMaior numero de acidentes: %d (%s)", 
           cadastro[iMaior].acidentes, cadastro[iMaior].nome);
    printf("\nMenor numero de acidentes: %d (%s)\n", 
           cadastro[iMenor].acidentes, cadastro[iMenor].nome);

    printf("\nPercentual de acidentes por estado:\n");
    for (int i = 0; i < ESTADOS; i++) {
        printf("%s: %.2f%%\n", cadastro[i].nome, percentualAcidentes(cadastro[i]));
    }

    media = mediaAcidentes(cadastro);
    printf("\nMedia nacional de acidentes: %.2f\n", media);

    acimaMedia(cadastro, media);

    return 0;
}
