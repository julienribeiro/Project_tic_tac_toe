# Project_tic_tac_toe
Projet Académique - M1 HETIC
Équipe : Fadi EL CHEIKH TAHA, Célia GUYOBON, Kevin SAGAN et Julien RIBEIRO

### Partie 1 : Objectifs

Dans le cadre d’un projet scolaire sur Python (“faire une simulation ou un jeu”), nous avons décidé de programmer un jeu de morpion. Par ailleurs du jeu, nous ont été donné les objectifs suivants:
* Concevoir le jeu en lui-même et permettre à deux joueurs humains de jouer l'un contre l'autre.
* Créer un programme qui joue aléatoirement au jeu.
* Créer un programme intelligent, qui ne laisse pas gagner l’adversaire et favorise la victoire.
* Créer une fonction qui permet de produire autant de fois que l'on souhaite un certain nombre de parties.
* Obtenir les statistiques de notre programme "intelligent".
* Faire une représentation graphique des statistiques du programme intelligent


### Partie 2 : Implémentation jeu morpion

Tout d'abord, nous avons importer toutes les librairies dont nous aurons besoin :
- random
- pandas
- matplotlib.pyplot

Nous avons développé l'intégralité de notre jeu à l'intérieur d'une classe : GameMorpion.

* Fonction d'initialisation du morpion : Possède 2 arguments : le type de joueur et le verbose :
  - Création d'une matrice (self.grid).
  - Création de la réponse du joueur 1 avec 'O' (self.answer_player_1).
  - Création de la réponse du joueur 2 avec 'X' (self.answer_player_2).
  - Création d'une liste vide qui va contenir des positions déjà joué (self.already_answer).
  - Création d'une variable pour le verbose (self.verbose).
  - Création d'une variable pour sélectionner le type de joueur entre 'human', 'ia_dumb_against_human', 'ia_smart_against_human', 'ia_dumb_against_ia_smart' et 'ia_smart_against_ia_smart' (self.type_player).
    
* Fonction de création du nom des joueurs humains (to_create_name_player) :
  - Création par input pour le nom du joueur 1 (self.player_1).
  - Création par input pour le nom du joueur 2 (self.player_2).
  
* Fonction de création de la grille du morpion (display_grid) :
  - Création et affichage de la grille par la boucle for.
  
* Fonction de création du programme qui joue aléatoirement (ia_dumb) :
  - Sélection de l'absisse pour le programme (x).
  - Sélection de l'ordonnée pour le programme (y).
  - Vérification si le programme sélectionne un emplacement déjà joué, si oui, on lui redemande.
  - Puis, ajout des coordonnées joué à l'intérieur de self.already_answer.
  
* Fonction de création du programme qui joue aléatoirement (ia_smart) :
  - Sélection de l'absisse pour le programme (x).
  - Sélection de l'ordonnée pour le programme (y).
  - Ajout des coordonnées joué à l'intérieur de self.already_answer.
  
* Fonction de création du programme qui joue aléatoirement (to_play_game) :
  - Sélection de l'absisse pour le programme (x).
  - Sélection de l'ordonnée pour le programme (y).
  - Ajout des coordonnées joué à l'intérieur de self.already_answer.
  
* Fonction de création du programme qui joue aléatoirement (verification) :
  - Sélection de l'absisse pour le programme (x).
  - Sélection de l'ordonnée pour le programme (y).
  - Ajout des coordonnées joué à l'intérieur de self.already_answer.
  
* Fonction de création du programme qui joue aléatoirement (to_launch_game) :
  - Sélection de l'absisse pour le programme (x).
  - Sélection de l'ordonnée pour le programme (y).
  - Ajout des coordonnées joué à l'intérieur de self.already_answer. 
    
### Partie 3 : Fonction pour X parties

### Partie 4 : Probabilités

### Partie 5 : Pie Chart

### Partie 6 : Conclusion

Afin de créer le programme "intelligent", nous avons décidé de le faire penser comme un humain, soit prioriser les tâches. 
Lorsqu’un humain joue au morpion:
* Il veut gagner à tout prix
* Il veut empêcher l’adversaire de gagner

Ainsi, les différentes techniques pour gagner/ empêcher l’adversaire de gagner - par ordre de priorité - sont:
Jouer les cases stratégiques pour la victoire, soient:
* La case du milieu
* Les coins
* Les cases sur les côtés


Observer les différents patterns de victoire. On simule le prochain tour de l’adversaire.
Lorsqu’une combinaison de 2 cases permet une victoire au prochain tour, alors on y met notre pion.
Nous avons ainsi créé un programme intelligent quasi-imbattable (84% de victoire), et qui arrive à raisonner en fonction de l’adversaire.

Le jeu du morpion étant assez simple (9 cases avec 3 issues possibles: victoire, défaite ou match nul), les 9 cases de ce jeu donnent tout de même  9! = 362 880 combinaisons de coups possibles. (le mouvement d’un joueur dépendant du précédent).
Notre programme raisonnant seulement en fonction du coup précédent et ne parvenant seulement à anticiper le coup suivant, (parallèle avec les échecs qui demande d’anticiper non pas un coup, mais un jeu entier)

