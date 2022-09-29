# Compte rendu TP 4 :
## Exercice 1 :
1 - Pour mettre a jour le système il faut taper les commandes :
    "sudo apt-get update"
    puis "sudo apt-get upgrade"

2 - Pour crééer un alias des commandes précedentes, on exécute :
    " alias maj="sudo apt-get update; sudo apt-get upgrade" " puis on l'ajoute à la fin de notre .bashrc pour qu'il soit permanent.

3 - Pour obtenir la liste des packets installées, j'utilise la commande :
    "cat /var/log/dpkg.log" ainsi pour les 5 derniers on à :
    " 2022-09-26 06:19:28 status half-configured install-info:amd64 6.8-4build1
    2022-09-26 06:19:28 status installed install-info:amd64 6.8-4build1
    2022-09-26 06:19:28 trigproc libc-bin:amd64 2.35-0ubuntu3.1 <none>
    2022-09-26 06:19:28 status half-configured libc-bin:amd64 2.35-0ubuntu3.1
    2022-09-26 06:19:28 status installed libc-bin:amd64 2.35-0ubuntu3.1 "

4 - En utilisant la commande : "cat /var/log/apt/history.log" on obtient l'historique de la gestion de paquets avec la compmande apt. On cherche alors les (ici 5) derniers paquets installés avec la commande "apt install" :
    bsdextrautils:amd64 (2.37.2-4ubuntu3, automatic), ubuntu-minimal:amd64 (1.481),
    iputils-tracepath:amd64 (3:20211215-1, automatic), 
    libparted2:amd64 (3.4-2build1, automatic), nftables:amd64 (1.0.2-1ubuntu2, automatic)

5 - Pour savoir combien de paquets on étés installés avec la commande apt on tape la commande suivante; le "wc -l" permet de compter le nombre de lignes donc le nombre de paquets :  "apt list --installed | wc -l" on à alors 615 paquets.
Pour les packets avec dpkg, on à 622 paquets. On à trouver ce nombre grace à la commande  "dpkg -l"
On trouve une petite différence car DPKG ne prends pas en compte les dépendances.

6 - Il y à 68953 paquets disponibles sur Ubuntu.

7 - Le paquet "glances" permet de voir les caractéristiques réseau.
    "tldr" permet de simplifier les vue du manuel.
    "hollywood" affiche des informations sur le réseau (tracer; affiche les trames) et surcharge l'utilisateur d'effets visuels.
    
8 - Le paquet "sudoku" permet de jouer au sudoku une fois installé.

## Exercice 2 :
La commande ls est installée depuis le paquet coreutils. On peut trouver les commandes grace à  "dpkg -S [commande ou chemin de la commande]".

Script "origine-commande" : 
    #!/bin/bash
    which -a $1 | xargs dpkg -S
    
## Exercice 3 :
Commande qui affiche le statut d'un paquet (installé ou non installé) :
    apt list lolo | grep "installed" && echo "Installé" || echo "non Installé"
    
## Exercice 4 :
Le "[" est un synonyme de la commande "test" qui permet de verifier le type d'un fichier.

## Exercice 5 :
A l'aie du curseur et de l'onglet "search" on cherche les paquets "ecmax" et "lynx " puis on les installes.

## Exercice 6 :
Note : c'est java17 qu'il faut instaler (dernière version)
Le nouveau fichier créer est "linuxuprising-ubuntu-java-jammy.list", il contient les liens de la source du paquet.
    
 ## Exercice 7 :
Pour compiler le logiciel bonsai on lit dans le README.dm qu'il faut taper les commandes : 
    "sudo apt install libncursesw5-dev"
    "sudo apt install cbonsai"
Puis pour executer on fait "cbonsai" ou "cbonsai -l" pour avoir l'animation.
    
En suite on installe "checkinstall" puis on verifie de n'imprte quel dossier que l'on peut executer "cbonsai".

## Exercice 8 :
    (fait, si besoin cf énoncé TP4)
