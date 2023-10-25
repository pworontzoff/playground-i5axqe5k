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
- génère un nombre entier compris entre 1 et 1000.
- offre à l’utilisateur 10 essais pour trouver ce nombre.  Les indications « c’est plus » ou « c’est moins » sont fournies à l’utilisateur pour toute tentative infructueuse.
- les tentatives qui sont hors de l'intervalle [1-1000] ne sont pas prises en compte (on garde le même nombre d'essais)
- Entrer 0 est synonyme d'abandon de la partie !

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