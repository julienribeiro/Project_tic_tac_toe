# Project_tic_tac_toe
Projet Académique - M1 HETIC
Équipe : Fadi EL CHEIKH TAHA, Célia GUYOBON, Kevin SAGAN et Julien RIBEIRO

### Partie 1

Autre que de développer le jeu du morpion avec le langage Python, nous avions plusieurs autres objectifs lors de ce projet:
* 1- Premièrement et la base était de concevoir le jeu en lui-même et de pouvoir laisser deux joueurs humain jouer l'un contre l'autre.
* 2- Créer un programme qui joue aléatoirement au jeu.
* 3- Créer un programme plus intelligent, qui favorise la victoire.
* 4- Créer une fonction qui permet de produire autant de fois que l'on souhaite un certain nombre de partie.
* 5- Obtenir des statistiques basique sur notre programme "intelligent".
* 6- Réaliser un graphique pour représenter les statistiques de notre programme.


### Implémentation

* Fonction d'initialisation du morpion : initialize() -> void
  - Utiliser la fonction 'querySelector' de l'API du DOM pour sélectionner uniquement les éléments 'td' à l'intérieur de la 'table' du morpion (classe CSS morpion) et obtenir un tableau (variable 'cells')
  - Utiliser la fonction forEach sur 'cells' et pour chaque élément
    - Ajouter le listener 'play' sur l'événement 'click'
    
L'intelligence artificielle se fonde sur l'hypothèse que le processus de pensée humain peut être mécanisé. Cela commence dès l’antiquité mais prend une toute autre empleur avec l’arrivé des composants électroniques au milieu des années 50.

Notre intelligence artificielle sera composée d’un algorithme, c’est à dire une suite d’instructions qui seront exécutées les unes après les autres, et d’une logique statistique, qui va étudier les cas possibles de jeu afin de gagner à chaque partie, notre intelligence artificielle ne pouvant donc jamais perdre.

Nous allons, dans un premier temps, construire le morpion en lui même, et ensuite y intégrer notre intelligence artificielle contre laquelle nous pourrons jouer.

Construction du morpion
Le morpion est un jeu de réflexion se pratiquant à deux joueurs au tour par tour, dont le but est de créer en premier un alignement de trois signes : des ronds ou des croix. Il tire son origine de l’Égypte Antique où ont été retrouvées des parties datant d’environ 1300 av. J.C.

Nous allons, grâce au langage Python, créer l’algorithme du morpion en lui même. Il sera composé de plusieurs fichiers :

game.py, qui se charge du déroulement général de la partie,
player.py, qui correspond aux données basiques de tout joueur, c'est à dire son signe, la fonction qui permet jouer,
human.py, qui est une implémentation de player.py, c’est à dire qu’il sera basé sur ce fichier en y ajoutant des fonctionnalités,
Et main.py, qui vient mettre tout ça ensemble et lancer la partie.
Commençons par game.py. Sa première fonction est la fonction d’initialisation de l’objet. Elle crée un tableau de jeu et enregistre les joueurs données par le fichier main.py que nous verrons plus loin.

Ensuite, vient la fonction start : elle démarre la partie et gère son déroulement. Une boucle fait jouer chaque joueur chacun leur tour jusqu’à ce qu’il y aie un gagnant ou un match nul (instruction while et for). A chaque tour elle affiche le tableau de jeu actuel (la fonction show, que nous verrons après), le joueur qui joue (la fonction print), et récupère le coup du joueur (fonction play que nous verrons également après). Elle est positionnée dans une boucle pour redemander au joueur son jeu s'il n’est pas valide (case déjà prise ou n’appartenant pas au tableau). Une fois ce processus terminé, elle affiche le gagnant, ou match nul si personne ne gagne.

Continuons avec la fonction show, elle se charge de parcourir le tableau pour l’afficher avec le numéro des lignes et des colonnes.

Puis la fonction play, vérifie la validité du coup (case libre dans les limites du tableau) et l'applique.

Vient ensuite la fonction win, qui vérifie tout le tableau dans des boucles pour savoir si un joueur a gagné ou non. Elle est couplé avec les fonctions line, col et dia qui vérifient chacune une ligne, une colonne ou une diagonale, pour simplifier le code et éviter les répétitions.

Pour terminer la fonction full qui permet de vérifier si le tableau est plein ou pas (pour les matchs nuls).

Passons ensuite au fichier player.py. Celui ci est très simple, il définit la structure de base d’un joueur, c’est à dire le signe (X ou O), et une fonction play pour lui permettre de jouer.

Il en découle donc le fichier human.py, l’implémentation de player.py. Il vient redéfinir la fonction play de player.py, en récupérant le jeu du joueur via le clavier.

Et pour finir vient le fichier main.py qui sera le fichier qui vient lancer le morpion. Il demande au joueur de choisir une configuration de jeu (qui joue contre qui), initialise l’objet game, et appelle la fonction start.

Maintenant passons à la partie intelligence artificielle de l’ordinateur, qui sera capable de “réfléchir” afin de sortir vainqueur à chaque partie, ou du moins forcer un match nul dans le cas ou il ne sera pas possible pour lui de gagner.
