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
  
  
