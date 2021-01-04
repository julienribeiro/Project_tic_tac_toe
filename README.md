# Project_tic_tac_toe
Projet Académique - M1 HETIC
Équipe : Fadi EL CHEIKH TAHA, Célia GUYOBON, Kevin SAGAN et Julien RIBEIRO

### Partie 1 : Objectifs

Dans le cadre d’un projet scolaire sur Python (“faire une simulation ou un jeu”), nous avons décidé de programmer un jeu de morpion. Par ailleurs du jeu, nous ont été donné les objectifs suivants:
* Concevoir le jeu en lui-même et permettre à deux joueurs humains de jouer l'un contre l'autre.
* Créer un programme qui joue aléatoirement.
* Créer un programme intelligent, qui ne laisse pas gagner l’adversaire et favorise la victoire.
* Créer une fonction qui permet de produire autant de fois que l'on souhaite un certain nombre de parties.
* Obtenir les statistiques de notre programme "intelligent".
* Faire une représentation graphique des statistiques du programme intelligent


### Partie 2 : Implémentation jeu morpion

Tout d'abord, nous avons importé toutes les librairies dont nous aurons besoin :
- random
- pandas
- matplotlib.pyplot

Nous avons développé l'intégralité de notre jeu à l'intérieur d'une classe : GameMorpion.

* Fonction d'initialisation du morpion : Possède 2 arguments : le type de joueur et le verbose :
  - Création d'une matrice (self.grid).
  - Création de la réponse du joueur 1 avec 'O' (self.answer_player_1).
  - Création de la réponse du joueur 2 avec 'X' (self.answer_player_2).
  - Création d'une liste vide qui va contenir des positions déjà joué (self.already_answer).
  - Création d'une variable verbose pour décider de l'affichage du jeu (self.verbose).
  - Création d'une variable pour sélectionner le type de joueur entre 'human', 'ia_dumb_against_human', 'ia_smart_against_human', 'ia_dumb_against_ia_smart' et 'ia_smart_against_ia_smart' (self.type_player).
    
* Fonction de création du nom des joueurs humains (to_create_name_player) :
  - Création par input pour le nom du joueur 1 (self.player_1).
  - Création par input pour le nom du joueur 2 (self.player_2).
  
* Fonction de création de la grille du morpion (display_grid) :
  - Création et affichage de la grille par la boucle for.
  
* Fonction de création du programme qui joue aléatoirement (ia_dumb) :
  - Sélection du numéro de ligne pour le programme (x).
  - Sélection du numéro de la colonne pour le programme (y).
  - Vérification si le programme sélectionne un emplacement déjà joué, si oui, on lui redemande.
  - Puis, ajout des coordonnées des coups joués à l'intérieur de self.already_answer.
  
* Fonction de création du programme qui joue intelligemment (ia_smart) :
  - Sélection du numéro de ligne pour le programme (x).
  - Sélection du numéro de la colonne pour le programme (y).
  - Vérification si le programme sélectionne un emplacement déjà joué, si oui, on lui redemande.
  - Vérification si le programme peut gagner au tour en question, si oui, il joue pour gagner.
  - Vérification si aucune position fait gagner le programme, alors il joue pour bloquer l'adversaire.
  - Si le programme joue en premier, il place tout le temps son premier pion au milieu soit (2, 2).
  - Si le programme joue en deuxième, si place du milieu vide, il place son pion dedans soit dans un coin au hasard.
  - Ajout des coordonnées des coups joués à l'intérieur de self.already_answer.
  
* Fonction qui permet à un humain de jouer (to_play_game) :
  - Sélection du numéro de ligne pour le joueur humain (x).
  - Sélection du numéro de la colonne pour le joueur humain (y).
  - Vérification si l'humain sélectionne un emplacement déjà joué, si oui, on lui redemande.
  - Ajout des coordonnées des coups joués à l'intérieur de self.already_answer.
  
* Fonction qui permet de vérifier si un joueur gagne (verification) :
  - Vérification sur les lignes, les colonnes et les diagonales.
  - Retourne le joueur gagnant.
  
* Fonction qui rassemble le tout et qui lance le jeu (to_launch_game) :
  - Appelle self.display_grid
  - Appelle self.to_create_name_player (si joueur humain)
  - Appelle self.ia_dumb (si l'ia dumb joue)
  - Appelle self.ia_smart (si l'ia smart joue)
  - Appelle self.to_play_game (si l'humain joue)
  - Appelle self.verification (pour la vérification d'un gagnant ou non)
  - Vérification si le jeu est fini et qu'il n'y a aucun gagnant alors retourne une égalité.
    
### Partie 3 : Fonction pour X parties

* Fonction qui permet de réaliser X parties (stats) : (attends 2 arguments, le type de partie et le nombre de parties)
  - Création d'une boucle for pour réaliser autant de fois que nous le souhaitons des parties de morpion.
  - Permet de compter aussi le nombre de victoires, défaites et matchs nuls (pour ici le programme intelligent).

### Partie 4 : Probabilités

Nous avons crée brièvement un print pour afficher le nombre de parties gagnée par le programme intelligent. Puis, nous en avons déduit un pourcentage de victoire sur 1000 parties. Nous sommes ici en général à 85% de victoires!

### Partie 5 : Pie Chart

Le pie chart à la toute fin du notebook permet de visualiser pour 1000 parties, le nombre de victoires, de défaites et de match nuls pour le programme intelligent.
Nous nous sommes servis de matplotlib pour créer ce diagramme circulaire. Nous pouvons apercevoir que nous avons environ 85% de victoires, 13% de matchs nuls et 1% de défaites (contre le programme qui joue aléatoirement).

### Conclusion

Afin de créer le programme "intelligent", nous avons décidé de le faire penser comme un humain, soit prioriser les tâches. 
Lorsqu’un humain joue au morpion:
* Il veut gagner à tout prix
* Il veut empêcher l’adversaire de gagner

Ainsi, les différentes techniques pour gagner/ empêcher l’adversaire de gagner - par ordre de priorité - sont:

1. Jouer les cases stratégiques pour la victoire, soient (dans l'ordre d'importance):
* La case du milieu
* Les coins
* Les cases sur les côtés


2. Observer les différents patterns de victoire. On simule le prochain tour de l’adversaire.
Lorsqu’une combinaison de 2 cases permet une victoire au prochain tour, alors on y met notre pion.
Nous avons ainsi créé un programme intelligent quasi-imbattable puisque comme visible sur notre pie chart, nous avons 1% de défaite. Notre programme arrive à raisonner en fonction de l’adversaire.


Bien que le jeu du morpion soit assez simple (9 cases avec 3 issues possibles: victoire, défaite ou match nul), les 9 cases de ce jeu donnent tout de même  9! = 362 880 combinaisons de coups possibles. (le mouvement d’un joueur dépendant du précédent).
Une programme "réflechissant comme un humain" est indubittablement efficace pour un jeu "simple" comme un morpion, mais arrivé à un certain niveau, il est normal de se demander si pour une application plus complexe, une autre méthode ne serait pas plus pertinente.
Notre programme raisonnant seulement en fonction du coup précédent et ne parvenant seulement à anticiper le coup suivant, nous pouvons faire un parallèle avec un jeu beaucoup plus complexe et technique: les échecs. Dans ce cas, battre les joueurs humains de manière quasi-systématique requièrerait d'anticiper non pas le prochain coup, mais tous les différents cas de figure - un jeu entier - et cela dès le premier coup sur un jeu totalisant 32 pions et 64 cases.

A l'heure actuelle, nous savons deux choses:
Ces exploits technologiques ont déjà été accomplis il y a plusieurs décennies et le domaine des intelligences artificielles est en croissance exponentielle.

Ainsi, nous pouvons nous poser une question:
Dans le cadre d'une simulation avec un nombre fini de possibilités, l'intelligence artificielle peut-elle remplacer l'humanité ?
