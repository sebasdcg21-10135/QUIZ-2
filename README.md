# QUIZ-2
Computación - Laboratorio 2

📌 PASO A PASO RESUMIDO – QUIZ 2 🚀

1️⃣ Crear el archivo en C
Abrir VS Code.
Crear un nuevo archivo llamado suma_polinomios.c.
Copiar y pegar el código:

#include <stdio.h>

#define MAX_GRADO 5 // Definimos el máximo grado permitido

// Función para imprimir un polinomio
void imprimirPolinomio(int polinomio[], int grado) {
    int primero = 1;
    for (int i = grado; i >= 0; i--) {
        if (polinomio[i] != 0) {
            if (!primero) {
                printf(" %c ", (polinomio[i] > 0) ? '+' : '-');
            } else {
                primero = 0;
                if (polinomio[i] < 0) {
                    printf("-");
                }
            }
            if (i == 0 || polinomio[i] != 1 && polinomio[i] != -1) {
                printf("%d", (polinomio[i] > 0) ? polinomio[i] : -polinomio[i]);
            }
            if (i > 0) {
                printf("x");
                if (i > 1) {
                    printf("^%d", i);
                }
            }
        }
    }
    printf("\n");
}

int main() {
    int numPolinomios, gradoMax;

    // Leer el número de polinomios y el mayor grado aceptado
    printf("Ingrese el número de polinomios: ");
    scanf("%d", &numPolinomios);
    printf("Ingrese el mayor grado aceptado: ");
    scanf("%d", &gradoMax);

    // Matriz para almacenar coeficientes (inicializada en 0)
    int coeficientes[numPolinomios][gradoMax + 1];
    int suma[gradoMax + 1];

    // Inicializar las matrices en 0
    for (int i = 0; i < numPolinomios; i++)
        for (int j = 0; j <= gradoMax; j++)
            coeficientes[i][j] = 0;

    for (int j = 0; j <= gradoMax; j++)
        suma[j] = 0;

    // Leer los polinomios
    for (int i = 0; i < numPolinomios; i++) {
        printf("\nPolinomio %d:\n", i + 1);
        int grado, coef;
        printf("Ingrese el grado del polinomio: ");
        scanf("%d", &grado);
        while (grado >= 0) {
            printf("Ingrese coeficiente de x^%d: ", grado);
            scanf("%d", &coef);
            coeficientes[i][grado] = coef;
            grado--;
        }
    }

    // Sumar los polinomios
    for (int i = 0; i < numPolinomios; i++)
        for (int j = 0; j <= gradoMax; j++)
            suma[j] += coeficientes[i][j];

    // Mostrar resultado
    printf("\nPolinomio resultante: ");
    imprimirPolinomio(suma, gradoMax);

    return 0;
}

2️⃣ Compilar y ejecutar el programa

Abrir la terminal en VS Code (Ctrl + ~ en Mac).
Compilar y ejercutar el código

3️⃣ Subir el código a GitHub
