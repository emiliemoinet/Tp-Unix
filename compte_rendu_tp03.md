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

et 'ls -l $1 | awk '{'print $3'}' pour vérifier le propriétaire du fichier.

![test-fichier](https://user-images.githubusercontent.com/90272616/137493312-970e167b-1b3e-46bf-a95e-20d0e9fc24b9.PNG)

### Afficher le contenu d'un répertoire

Création d'un listedir.sh comme les fichiers précédent.
'ls -lkF $1 | grep -v '/' | awk '{print $9}' permet d'afficher uniquement les fichiers tandis que si on enlève le "-v" cela
permet d'afficher uniquement les répertoires. 

![listedir](https://user-images.githubusercontent.com/90272616/137497113-8d61e047-c54c-4ec4-b21c-b85f68f0386f.PNG)

Ce qui donne lors du test : 

```
root@serveur1:~# ./listedir.sh /boot
## fichier dans /boot/
/boot/config-5.10.0-8-amd64
/boot/initrd.img-5.10.0-8-amd64
/boot/System.map-5.10.0-8-amd64
/boot/vmlinuz-5.10.0-8-amd64
## répertoire dans /boot/
/boot/folder/
```

### Lister les utilisateurs

Création d'un script bash list-user.sh celui-ci ayant pour but d'afficher la liste des noms de login des utilisateurs avec un UID supérieur à 100.

![list_user](https://user-images.githubusercontent.com/90272616/137499599-943cc998-3dc5-4576-a4db-ea0daf122bb2.PNG)

```
root@serveur1:~# ./list-user.sh
nobody:65534
systemd-timesync:101
systemd-network:102
systemd-resolve:103
messagebus:104
systemd-coredump:999
sshd:105
```
