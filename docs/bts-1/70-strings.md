# Les chaînes de caractères

<object class="fullScreenAble" data="../../pdf/cours/bts1/bts1_09_tableaux_2.pdf" type="application/pdf"></object>

## Exercice 8

Ecrire un programme exo_8.c qui affiche le deuxième, le quatrième et le septième caractère d'une chaîne saisie au clavier (10 caractères maximum).

??? success "Solution"

    ```c
    #include <stdio.h>
    #include <string.h>

    int main() {
        char input[11] = "";

        printf("Saisir une chaine de 10 caracteres : ");

        while (strlen(input) != 10) {
            gets(input);
        }

        printf("Caracteres  n°2 : %c, n°4 : %c et n°7 : %c\n", input[1], input[3], input[6]);

        return 0;
    }
    ```

## Exercice 9

Ecrire un programme exo_9.c qui :

1.  d'abord, crée une chaîne de caractères (20 caractères maximum),

2.  puis, y stocke la saisie de l'utilisateur lue caractère par caractère jusqu'à ce que la chaîne soit remplie,

    ??? warning "Oh oh... 😣"

        Des difficultés à lire successivement des caractères ?

        Qu'est-ce qu'on a dit **en cours** sur `scanf` et sa mémoire tampon (buffer) ?

3.  ensuite, affiche la chaîne,

4.  finalement, affiche la chaîne en ordre inverse.

??? success "Solution"

    ```c
    #include <stdio.h>
    #include <stdlib.h>

    int main() {
        
        char string[21] = "", temp;

        system("chcp 65001");
        system("cls");

        puts("Saisir 20 caractères :");
        for (int i = 0; i < 20; i++) {
            printf("#%02d : ", i + 1);
            
            // Lecture caractère par caractère
            scanf("%c", string + i);
            // 💡 Pour se débarasser du '\n' qui reste dans le buffer de scanf !
            scanf("%c", &temp); 

            // Autre solution :
            // char input[2];
            // gets(input);
            // sscanf(input, "%c", string + i);
        }

        // On n'oublie pas de mettre un \0 à la fin
        string[20] = '\0';

        // Affichage dans l'ordre
        printf("\nChaîne saisie : %s\n", string);

        // Affichage dans l'ordre inverse
        printf("\nChaîne saisie en ordre inverse : ");
        for (int i = 19; i >= 0; i--) {
            printf("%c", string[i]);
        }
        printf("\n");

        return 0;
    }
    ```

## Exercice 10

Ecrire un programme exo_10.c qui affiche le nombre de fois où le caractère 'a' est présent dans la chaîne "It's gonna be legend... wait for it... dary!".

??? success "Solution"

    ![Minute papillon...](../images/meme/waiting-barney.gif)
    

## Exercice 11

Reprendre l'exercice 10 dans un nouveau programme exo_11.c :

1. En rendant le **caractère** et la **chaîne** saisissables par l'utilisateur.

2. En recherchant minuscule et majuscule du caractère saisi pour les 26 lettres non accentuées.

??? success "Solution"

    ![Minute papillon...](../images/meme/oups-kristen.gif)

