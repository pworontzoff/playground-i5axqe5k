# Exercice 3

## Les nombres aléatoires : un petit exemple

```C runnable
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

int main() {
	//Initialise la séquence de nombres pseudo-aléatoires
	srand(time(NULL));

	//rand() renvoi un nombre pseudo-aléatoire.
	printf("Nombre aléatoire 1 : %d\n", rand());
	printf("Nombre aléatoire 2 : %d\n", rand());
	printf("Nombre aléatoire 3 : %d\n", rand());
	
	return 0;
}
```


## L'énoncé : devinez le nombre ! 

Ecrire un programme qui …
- Génère un nombre entier compris entre 1 et 1000;
- Offre à l’utilisateur 10 essais pour trouver ce nombre.  Les indications « c’est plus » ou « c’est moins » sont fournies à l’utilisateur pour toute tentative infructueuse;
- NB : Les tentatives qui sont hors de l'intervalle [1-1000] ne sont pas prises en compte (on garde le même nombre d'essais);
- NB : Entrer 0 est synonyme d'abandon de la partie.

Le programme doit générer les affichages suivants (en fonction des scenari : défaite, abandon ou vicroire):

Exemple de défaite :
```
Deviner le nombre entre 1 et 1000 (0 pour abandonner) :
1
C'est plus ! Il te reste 9 essais...
2
C'est plus ! Il te reste 8 essais...
3
C'est plus ! Il te reste 7 essais...
4
C'est plus ! Il te reste 6 essais...
5
C'est plus ! Il te reste 5 essais...
6
C'est plus ! Il te reste 4 essais...
7
C'est plus ! Il te reste 3 essais...
8
C'est plus ! Il te reste 2 essais...
9
C'est plus ! Il te reste 1 essais...
10
C'est plus ! Il te reste 0 essais...

C'est perdu, le nombre a devine etait : 179 !
```

Exemple d'abandon :
```
Deviner le nombre entre 1 et 1000 (0 pour abandonner) :
-1
Essai non pris en compte !
1001
Essai non pris en compte !
500
C'est moins ! Il te reste 9 essais...
1
C'est plus ! Il te reste 8 essais...
0
Abandon !

C'est perdu, le nombre a devine etait : 252 !
```

Exemple de victoire :
```
Deviner le nombre entre 1 et 1000 (0 pour abandonner) :
500
C'est plus ! Il te reste 9 essais...
750
C'est moins ! Il te reste 8 essais...
600
C'est plus ! Il te reste 7 essais...
675
C'est moins ! Il te reste 6 essais...
635
C'est plus ! Il te reste 5 essais...
655
C'est plus ! Il te reste 4 essais...
665
C'est plus ! Il te reste 3 essais...
670
C'est moins ! Il te reste 2 essais...
668
C'est moins ! Il te reste 1 essais...
667
C'est gagne !
```

Attention, votre chef a programmé le main pour vous comme ceci, il vous reste à terminer le programme (sans pouvoir changer le code donné) : 

```C
#pragma warning(disable:4996)
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int jeu(int nbEssais, int n, int x); // prend en argument le nombre d'essais restants (nbEssais), le nombre à deviner (n) et le nombre entré par l'utilisateur (x) et retourne le nombre d'essais restants actualisés.

int main() {
    int n; // le nombre à deviner.
    int x; // le nombre entré par l'utilisateur (un essai)
    int nbEssais = 10;
    //Initialise la séquence de nombres pseudo-aléatoires
    srand((unsigned int)time(NULL));

    n = rand() % 1000 + 1;

    printf("Deviner le nombre entre 1 et 1000 (0 pour abandonner) :\n");
    do {
        scanf("%d", &x);
        nbEssais = jeu(nbEssais, n, x);
    } while (nbEssais > 0 && x != n && x != 0);
    if (x != n) {
        printf("\nC'est perdu, le nombre a devine etait : %d !\n", n);
    }
    return 0;
}
```