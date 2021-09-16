# Compte rendu TP 02 Unix

## Secure Shell : SSH
### Connection SSH root

  Grâce à la commande man sshd_config, on accède au fichier sshd_config dont on cherche PermitRootLogin. Celui-ci permet à root de se connecter en utilisant ssh ou pas.
  Si cette option est activée sur prohibit-password alors il est impossible de se connecter avec un mot de passe ou une action du clavier. 
  Tandis que si cette options est mise sur forced-commands-only, alors le login root grâce à une clé d'authentification sera autorisé seulement si l'option de commande est spécifié. Toutes les autres méthodes d'authentification sont désactivées pour root. 
  
### Authentification par clef / Génération de clefs

  Grâce à la commande ssh-keygen, on peut générer des clefs public ou private et récupérer celle qui est utile à l'étape suivante.

### Authentification par clef / Connection serveur

  Grâce à la commande nano ~/.ssh/authorized_key qui ouvre le fichier .ssh qui n'existait pas auparavant, il a fallu récupérer et coller la clé suivante :
- SHA256:EHdAZjQoh9Qgua1VsFYyEnuUfQGT9+Y+7fkLY7Eh4fA root@serveur1


### Authentification par clef : sous Windows!

![image](https://user-images.githubusercontent.com/90272616/133579180-e5ffa7d1-4acb-4db9-a429-f52653dd46d4.PNG)

ssh -i ./id_rsa root@134.157.46.209

###  Sécurisez

## Processus
### Etude des processus UNIX

1)  L'information TIME correspond au temps CPU cumulé, utilisateur plus système. Le format d'affichage est normalement « MMM:SS », mais peut être déplacé vers la droite si des processus ont cumulé plus de 999 minutes de temps CPU.
  Les processus ayant le plus utilisés le processeur sur la machine sont les procesus avec le numéro d'identification 1 et 453.
  Le premier processus lancé après le démarrage de la machine sont les procesus avec comme numéro d'identification allant de 1 à 418.
  Avec la commande uptime, on peut récupérer l'heure de démarrage de la machine 
  root@serveur1:~# uptime
 11:52:58 up 52 min,  2 users,  load average: 0,00, 0,00, 0,00
 Avec la commande ps -e on peu récupérer le nombre approximatif de processus crée depuis le démarrage de la machine, celui-ci étant d'environ 636.

2)  Pour afficher le PPID, l'option de commande de ps est ps -ef

3)  Pour utiliser la commande pstree, il a fallu d'abord l'installer avec la commande apt install psmisc. 

root@serveur1:~# pstree
systemd─┬─cron
        ├─dbus-daemon
        ├─login───bash
        ├─rsyslogd───3*[{rsyslogd}]
        ├─sshd───sshd───bash───pstree
        ├─systemd───(sd-pam)
        ├─systemd-journal
        ├─systemd-logind
        ├─systemd-timesyn───{systemd-timesyn}
        └─systemd-udevd
      
      
4) top ? puis x pour choisir la meémoire
PID UTIL.     PR  NI    VIRT    RES    SHR S  %CPU  %MEM    TEMPS+ COM.
      1 root      20   0   98204  10044   7716 S   0,0   1,0   0:02.35 systemd
      
      systemd, init - systemd system and service manager est le plus gros processus de la machine, il correspond au système de service et de management pour les systèmes d'opérations linux. 
      Pour changer la couleur d'affichage il faut faire top puis z et grâce Z on peut choisir la couleur de notre choix. Pour changer de colonne de trie il faut utiliser la touche < et >, pour mettre en avant une colonne il suffit d'utiliser la touche x.
      htop permet de lister et gérer les processus. Ils sont des équivalents de “top” qui est installé par défaut sur les systèmes GNU-Linux. 
    Démarrant plus rapidement, il offre un certain nombre d’avantages par rapport à son grand frère, notamment :
-interface plus conviviale et adaptée à la taille de l’affichage,
-possibilité de killer un processus sans connaître son PID,
-possibilité de modifier en live la priorité (nice) d’un processus sans connaître son PID,
-pas de délai entre les actions,
-support de la souris,
-plus récent que top (1984) (et htop (2004))

Cependant il est rarement préinstaller sur la plupart des distributions Linux. Une installation manuelle est nécessaire.

## Arrêt d’un processus

     
 
  
