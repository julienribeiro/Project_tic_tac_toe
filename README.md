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
  - Ajout des coordonnées joué à l'intérieur de self.already_answer.
  
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
