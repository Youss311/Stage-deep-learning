# Stage-deep-learning
Calcul de l'augmentation de l'incertitude et la perte de couverture après une projection monopartite d'un graphe bipartite.

- Ce code calcul la perte de couverture et l'augmentation de l'incertitude engendrés après projection monopartite d'un graphe bipartite.

- Il prend en input le jeu de donnée que nous voulons étudier, tous les fichiers contenant les colonnes suivantes ou des colonnes similaires
 pourront etre étudiés avec ce code :
  a-colonne nom drug (nom du médicament).
  b-colonne nom de la maladie ou de la cyble ou de l'effet secondaire engendré par le medicament.
  c-colonne id-drug (un identifiant pour les médicaments.
  d-colonne nom de la famille à laquelle appartient cette cyble ou maladie ou effet secondaire.

-Pour pouvoir lancer ce code il faut:
  a- Avoir une version de R supérieure à 3.5 
  b- Installer Rmarkdown sur R studio 
  c- Installer le package "reticulate" sur r studio 
Toutes les explication en ce qui concerne le package "reticulate" sont sur le tuto joint à ce Read-me.

Avant de lancer le code il faut mettre le nombre de familles (socs ou classes de recepteurs) sur les quelles nous voulons 
travailler en modifiant la variable "nbr_familles" , toutes les informations necessaires et explications concernanat les valeurs a mettre pour
les deux jeu de données "Drug-target" et "Drug-EffetSecondaire" sont mises en commentaire ou avant chaque chunk du fichier Rmarkdown contenant le code.

-Ce code renvoie en output 2 tableaux : 
  1- "tableau_perte_information.csv" Contenant les pertes d'informations calculées.  
  2- "Recap_graph_monopartite.csv" Contenant un récapitulatif de la structure du graphe monopartite généré.
  -la ligne de commande suivante permet de lire ces deux fichiers :
   read.table("nom fichier contenant tableau", sep="\t",dec=".").
    ou 
   read.csv("nom fichier contenant tableau").

-Ce code renvoie aussi 3 pdf en output
  1- boxplot_augmentation_incertitude.pdf
  2- boxplot_perte_de_couverture.pdf
ces boxplote donnent la distribution de la perte d'information pour chaque famille de target ou de soc
  3- "Relation_expo_Cov_H.pdf" contenant un plot de la relation entre la perte de couverture et l'augmentation de l'incertitude , où chaque point 
représente un target ou un effet secondaire.
