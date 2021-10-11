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

Création d'un script concat.sh de la manière que le script précédent.
![concat](https://user-images.githubusercontent.com/90272616/136800554-f0a379f8-7d09-40cb-a780-c86ef757976a.PNG)
