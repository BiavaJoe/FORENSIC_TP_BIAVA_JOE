Exercice à réaliser :

Le fichier consommation-annuelle-residentielle-par-adresse.csv a été fourni afin de recenser la consommation annuelle résidentielle en France. Notre service travaillant pour Toulouse aurait besoin de récupérer le nombre de personnes recensées habitant à Toulouse.

Consigne :

Aidez notre service toulousain à obtenir l'information. Attention, certaines lignes sont écrites en minuscules et d'autres en majuscules, et nous avons besoin du nombre COMPLET des habitant de Toulouse.
Nous avons compté pour notre part 6799 personnes, pouvez-vous nous le confirmer ?


Correction :
Afin d'obtenir les informations la ville dans le fichier csv, nous avons tout d'abord besoin de la commande 
	awk -F";" '{print $9}' consommation-annuelle-residentielle-par-adresse.csv
Cela nous permettra de récupérer toutes les villes (qui est le 9ème champ du fichier CSV délimité par le caractère ";")

Ensuite, afin de ne pas être géné par la syntaxe, nous utilisons l'outil tr, afin de mettre tout les caractères en majuscule
	tr [:lower] [:upper]
Maintenant, tout les résultats sont écrits en majuscules

Nous allons maintenant limiter le nombre de résultat à la ville TOULOUSE grâce à l'outil grep
	grep "TOULOUSE"
Nous avons maintenant le retour de toutes les lignes où il est inscrit OULOUSE

Enfin, nous allons compter le nombre de lignes retournées maintenant que les bonnes informations sont retournées grâce à l'outil wc
	wc -l
Cela va donc compter le nombre de ligne que les commandes précédentes auront retournées.

La ligne complète pour trouver le résultat est :
	awk -F";" '{print $9}' consommation-annuelle-residentielle-par-adresse.csv | tr [:lower] [:upper] | grep "TOULOUSE" | wc -l
Le résultat attendu est 6799.

