# Compte rendu TP 03 Unix

## Shell Bash

### Paramètres

Création d'un script analyse.sh avec nano,  puis dans le script écrire en haut "#!/bin/bash" puis le texte imposé. 
- $# pour obtenir le nombre de paramètres rentré,
- $0 pour obtenir le nom du script en cours d'exécution,
- $i pour obtenir le nième paramètre i pouvant aller de 1 à 9,
- $@ pour obtenir la liste de tout les paramètres séparés par un espace,

Pour exécuter le fichier : ./analyse.sh si la permission n'est pas accordé vérifier avec ls -alh, puis rajouter les droits manquant ici "chmod o+x analyse.sh".

### Vérification du nombre de paramètres

Création d'un script concat.sh de la même manière que le script précédent. Celui-ci contenant une boucle par rapport au nombre de paramètres : 
![concat](https://user-images.githubusercontent.com/90272616/136800554-f0a379f8-7d09-40cb-a780-c86ef757976a.PNG)

### Argument type et droits

Création d'un script test-fichier.sh de la même manière que les deux scripts précédent. 
Vérification de l'existence du fichier avec " if [ -e $1 ] "

Vérification du type de fichier avec " if [ -d $1 ] " pour le répertoire et " if [ -f $1 ] " pour les fichiers.

Vérifier les droits avec : 
- -r
- -w
- -x

![test-fichier](https://user-images.githubusercontent.com/90272616/136806942-20a9184a-1652-4eed-a530-172b948a2168.PNG)



