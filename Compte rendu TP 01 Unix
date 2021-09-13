# Compte rendu TP 01 Unix

## La seconde partie du TP consiste à faire une configuration SSH. 
Celle-ci à pour but de permettre une connexion à distance sur une machine et également transférer des fichiers si la machine dispose 
d’un serveur SSH.
Pour permettre la configuration SSH, nous avons monté une machine virtuelle sur Virtual Box ainsi que 
- configurer la langue, 
- le clavier, le réseau, 
- choisir un miroir d’installation et l’installer, 
- configurer un mot de passe, l’horloge, 
- détecter les disques et les partitionner manuellement, 
- installer un système de base ainsi que kernel. 
- configurer un paquet manager, 
- installer un software puis grub. 

Une fois la machine créée et configurer, on peut passer à la configuration du SSH.  
La première étape de la configuration consiste à faire une mise à jour à l’aide de la commande « apt update » puis 
d’installer SSH serveur, il faut également modifier le fichier config de SSH. 
- Enregistrer le fichier et redémarrer le service avec la commande « service ssh restart ».
- Ensuite il faut installer cmder depuis google et l’extraire, éteindre la machine virtuelle et 
changer le mode d’accès au réseau en bridge. 
- Configurer une adresse IP statique plutôt qu’ne DHCP (134.157.46.209). 
- Aller de nouveau dans le fichier ssh-config et décommenter la ligne « permitRootLogin yes ».
Enfin, pour se connecter en SSH il faut la commande « ssh root@ip134.157.46.209 », 
puis utiliser « dpkp -l | wc -l » ce qui permet de consulter les informationsdes fichiers systèmes comme :
- l’espace utilisé, 
- la place disponible, 
- la taille, 
- son utilisation en pourcentage 
- et sur quel chemin il est monté. 

Pour finir, il faut reset son adresse IP grâce à la commande « ip  /etc /network/interfaces ». 
