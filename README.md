1- 

#include <stdio.h>

int main() {
    int numProdutos, valorLimite, contador = 0;
    float preco;

    printf("Digite o número de produtos: ");
    scanf("%d", &numProdutos);

    printf("Digite o valor limite: ");
    scanf("%f", &valorLimite);

    for (int i = 0; i < numProdutos; i++) {
        printf("Digite o preço do produto %d: ", i + 1);
        scanf("%f", &preco);

        if (preco < valorLimite) {
            contador++;
        }
    }

    printf("Número de produtos abaixo do valor limite: %d\n", contador);

    return 0;
}


2-

#include <stdio.h>
#include <string.h>

#define MAX_PRODUTOS 100 

struct Produto {
    int id;
    char nome[50];
    float valor;
};

int buscarProduto(struct Produto produtos[], int numProdutos, int idBusca) {
    for (int i = 0; i < numProdutos; i++) {
        if (produtos[i].id == idBusca) {
            return i; // Retorna o índice do produto encontrado
        }
    }
    return -1; 
}

int main() {
    struct Produto produtos[MAX_PRODUTOS];
    int numProdutos = 0;

    int idBusca;
    printf("Digite o ID do produto que deseja buscar: ");
    scanf("%d", &idBusca);

    int indice = buscarProduto(produtos, numProdutos, idBusca);
    if (indice != -1) {
        printf("Produto encontrado:\n");
        printf("ID: %d\n", produtos[indice].id);
        printf("Nome: %s\n", produtos[indice].nome);
        printf("Valor: R$ %.2f\n", produtos[indice].valor);
    } else {
        printf("Produto não encontrado.\n");
    }

    return 0;
}

3-

#include <stdio.h>
#include <string.h>

#define MAX_PRODUTOS 100

struct Produto {
    int id;
    char nome[50];
    float valor;
};

int buscarProduto(struct Produto produtos[], int numProdutos, int idBusca) {
    for (int i = 0; i < numProdutos; i++) {
        if (produtos[i].id == idBusca) {
            return i; 
        }
    }
    return -1; 
}

int main() {
    struct Produto produtos[MAX_PRODUTOS];
    int numProdutos = 0;

    int idAtualizar, indice;
    float novoValor;

    printf("Digite o ID do produto que deseja atualizar: ");
    scanf("%d", &idAtualizar);

    indice = buscarProduto(produtos, numProdutos, idAtualizar);
    if (indice != -1) {
        printf("Digite o novo valor do produto: ");
        scanf("%f", &novoValor);

        produtos[indice].valor = novoValor;
        printf("Valor do produto atualizado com sucesso!\n");
    } else {
        printf("Produto não encontrado.\n");
    }

    return 0;
}


4-

#include <stdio.h>

float calcularMedia(float precos[], int numProdutos) {
    float soma = 0;
    for (int i = 0; i < numProdutos; i++) {
        soma += precos[i];
    }
    return soma / numProdutos;
}

int main() {
    int numProdutos;
    printf("Digite o número de produtos: ");
    scanf("%d", &numProdutos);

    float precos[numProdutos];
    printf("Digite os preços dos produtos:\n");
    for (int i = 0; i < numProdutos; i++) {
        scanf("%f", &precos[i]);
    }

    float media = calcularMedia(precos, numProdutos);
    printf("A média dos preços é: %.2f\n", media);

    return 0;
}


5- 

#include <stdio.h>
#include <string.h>

#define MAX_PRODUTOS 100 // Ajuste este valor conforme necessário

struct Produto {
    int id;
    char nome[50];
    float valor;
};

int main() {
    struct Produto produtos[MAX_PRODUTOS];
    int numProdutos = 0;

    float soma = 0;
    for (int i = 0; i < numProdutos; i++) {
        soma += produtos[i].valor;
    }
    float media = soma / numProdutos;

    printf("Produtos com preço acima da média (%.2f):\n", media);
    for (int i = 0; i < numProdutos; i++) {
        if (produtos[i].valor > media) {
            printf("ID: %d, Nome: %s, Valor: R$ %.2f\n",
                   produtos[i].id, produtos[i].nome, produtos[i].valor);
        }
    }

    return 0;
}


6-

#include <stdio.h>

#define MAX_CLUBES 10

struct clube {
    int id;
    char nome[50];
    int vitorias, empates, derrotas, gols_pro, gols_contra;
    int pontos;
};

int main() {
    struct clube clubes[MAX_CLUBES];
    int num_clubes, i;

    printf("Digite o número de clubes (máximo %d): ", MAX_CLUBES);
    scanf("%d", &num_clubes);

    for (i = 0; i < num_clubes; i++) {
        printf("\nClube %d:\n", i+1);
        printf("ID: ");
        scanf("%d", &clubes[i].id);
        printf("Nome: ");
        scanf("%s", clubes[i].nome);
        printf("Vitórias: ");
        scanf("%d", &clubes[i].vitorias);
        printf("Empates: ");
        scanf("%d", &clubes[i].empates);
        printf("Derrotas: ");
        scanf("%d", &clubes[i].derrotas);
        printf("Gols pró: ");
        scanf("%d", &clubes[i].gols_pro);
        printf("Gols contra: ");
        scanf("%d", &clubes[i].gols_contra);

        clubes[i].pontos = clubes[i].vitorias * 3 + clubes[i].empates;
    }

    printf("\nPontuação dos clubes:\n");
    for (i = 0; i < num_clubes; i++) {
        printf("%s: %d pontos\n", clubes[i].nome, clubes[i].pontos);
    }

    return 0;
}

7-

#include <stdio.h>

int main() {

    int id_buscado;

    printf("\nDigite o ID do clube que deseja buscar: ");
    scanf("%d", &id_buscado);

    int encontrado = 0;
    for (i = 0; i < num_clubes; i++) {
        if (clubes[i].id == id_buscado) {
            printf("\nClube encontrado:\n");
            printf("ID: %d\n", clubes[i].id);
            printf("Nome: %s\n", clubes[i].nome);
            printf("Vitórias: %d\n", clubes[i].vitorias);
            printf("Empates: %d\n", clubes[i].empates);
            printf("Derrotas: %d\n", clubes[i].derrotas);
            printf("Gols pró: %d\n", clubes[i].gols_pro);
            printf("Gols contra: %d\n", clubes[i].gols_contra);
            printf("Pontos: %d\n", clubes[i].pontos);
            encontrado = 1;
            break;
        }
    }

    if (!encontrado) {
        printf("Clube não encontrado.\n");
    }

    return 0;
}

8-

#include <stdio.h>

#define MAX_CLUBES 10

struct clube {
    int id;
    char nome[50];
    int vitorias, empates, derrotas, gols_pro, gols_contra;
    int pontos;
};

int main() {
    struct clube clubes[MAX_CLUBES];
    int num_clubes, i;

    int soma_gols_pro = 0;

    for (i = 0; i < num_clubes; i++) {
        soma_gols_pro += clubes[i].gols_pro;
    }
    float media_gols_pro = (float) soma_gols_pro / num_clubes;

    printf("\nMédia de gols pró: %.2f\n", media_gols_pro);
    printf("\nClubes com gols pró acima da média:\n");
    for (i = 0; i < num_clubes; i++) {
        if (clubes[i].gols_pro > media_gols_pro) {
            printf("%s: %d gols pró\n", clubes[i].nome, clubes[i].gols_pro);
        }
    }

    return 0;
}


9-

#include <stdio.h>

#define MAX_CLUBES 10

struct clube {
    int id;
    char nome[50];
    int vitorias, empates, derrotas, gols_pro, gols_contra;
    int pontos, saldo_gols;
};

int main() {
    struct clube clubes[MAX_CLUBES];
    int num_clubes, i;

    for (i = 0; i < num_clubes; i++) {
        clubes[i].saldo_gols = clubes[i].gols_pro - clubes[i].gols_contra;
    }

    printf("\nSaldo de gols de cada clube:\n");
    for (i = 0; i < num_clubes; i++) {
        printf("%s: %d\n", clubes[i].nome, clubes[i].saldo_gols);
    }

    return 0;
}

10-

#include <stdio.h>

#define MAX_CLUBES 10

struct clube {
    int id;
    char nome[50];
    int vitorias, empates, derrotas, gols_pro, gols_contra, pontos, saldo_gols;
};

int main() {
    struct clube clubes[MAX_CLUBES];
    int num_clubes, i;

    int indice_campeao = 0, indice_ultimo = 0;
    for (i = 1; i < num_clubes; i++) {
        if (clubes[i].pontos > clubes[indice_campeao].pontos) {
            indice_campeao = i;
        } else if (clubes[i].pontos < clubes[indice_ultimo].pontos) {
            indice_ultimo = i;
        }
  
        else if (clubes[i].pontos == clubes[indice_campeao].pontos && clubes[i].saldo_gols > clubes[indice_campeao].saldo_gols) {
            indice_campeao = i;
        } else if (clubes[i].pontos == clubes[indice_ultimo].pontos && clubes[i].saldo_gols < clubes[indice_ultimo].saldo_gols) {
            indice_ultimo = i;
        }
    }

    printf("\nCampeão:\n");
    printf("Nome: %s\n", clubes[indice_campeao].nome);
    printf("Pontos: %d\n", clubes[indice_campeao].pontos);
    printf("Saldo de gols: %d\n", clubes[indice_campeao].saldo_gols);

    printf("\nÚltimo colocado:\n");
    printf("Nome: %s\n", clubes[indice_ultimo].nome);
    printf("Pontos: %d\n", clubes[indice_ultimo].pontos);
    printf("Saldo de gols: %d\n", clubes[indice_ultimo].saldo_gols);

    return 0;
}



