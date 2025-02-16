# Exercice 1

Afin de pouvoir mieux combattre les différentes épidémies, parfois très graves, qui se développent régulièrement dans la région, le département de médecine de l'université a lancé une grande étude. En particulier, les chercheurs s'intéressent à la vitesse de propagation d'une épidémie et donc à la vitesse à laquelle des mesures sanitaires doivent être mises en place.

Votre programme doit d'abord lire un nombre entier correspondant à la population totale de la ville. Sachant qu'une personne était malade au jour 1 et que chaque malade contamine deux nouvelles personnes le jour suivant (et chacun des jours qui suivent), vous devez calculer à partir de quel jour toute la population de la ville sera malade.

Vous devrez impérativement programmer une solution qui utilise la fonction suivante, dont voici le prototype imposé : 

```c
int doomsDay(int pop); // pop : la population de la ville (nombre de'habitants). 
                       // Retourne le nombre de jours nécéssaires pour que toute la ville soit malade.
```

Rappelons que pour que la fonction `doomsDay()` retourne un nombre `n`, il faudra écrire à la fin de la définition de cette fonction : 

```c
return n;
```

Et dans le code appelant (dans le `main()`) `doomsDay(pop)` est vu comme le nombre retourné !


## Exemple

On a 1 malade le premier jour, donc 2 nouveaux malades le second jour, soit un total de 3 malades. On a donc 6 nouveaux malades au troisième jour, soit un total de 9 malades. On a donc 18 nouveaux malades au quatrième jour, soit…
