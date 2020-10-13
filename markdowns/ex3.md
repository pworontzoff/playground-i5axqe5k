# Exercice 3

## Les nombres aléatoires

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


## Devinez le nombre ! 

Ecrire un programme qui …
- génère un nombre entier compris entre 1 et 1000.
- offre à l’utilisateur 10 essais pour trouver ce nombre.  Les indications « c’est plus » ou « c’est moins » sont fournies à l’utilisateur pour toute tentative infructueuse.
