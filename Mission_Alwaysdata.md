## Etape 0 : Créer un espace sur Alwaysdata

Créer un compte sur Alwaysdata gratuit (100 Mo).

- Quels services sont offerts par Alwaysdata ?

        Alwaysdata est un fournisseur de services d'hébergement web. Ce fournisseur propose de l'hébergement de sites web, d'applications web, de gestion de domaines et du support technique pour aider ses clients.
- Quels services seront nécessaires pour déployer un site web (HTML, CSS, JS et PHP) ?

        Pour déployer un site web, vous aurez besoin du service d'hébergement web prenant en charge ces langages, ainsi que d'un serveur capable d'exécuter du code.
- Quel est le nom de domaine choisi pour le déploiement de votre site ? (**Attention** : choisir un nom sans `-`(tiret du 6))

## Etape 1 : Activer SSH

Pour ajouter les fichiers de votre site web à votre espace, il faut activer votre accès ssh.

- Expliquer l'intérêt du protocole SSH. Sur quel port est-il actif par défaut ? 

        Le protocole SSH permet aux utilisateurs d’établir une connexion sécurisée entre deux ordinateurs afin de transférer des fichiers de manière sécurisée. Par défaut, le protocole SSH est actif sur le port 22. Cependant, il est souvent recommandé de modifier ce port par défaut pour des raisons de sécurité
- Quel autre protocole semble avoir les mêmes fonctionnalités ? Que fait SSH qui n'est pas possible avec le 2e ?

        Le protocole FTP propose aussi du transfert de fichiers, mais la principale différence se situe dans la partie sécurité. En effet, le SSH chiffre les données échangées tandis que le FTP envoie simplement les données en texte claire. Le FTP n'offre pas de sécurisation.
- Activer un accès au serveur via ce protocole. Quelles étapes sont nécessaires ?

        Nous devons nous connecter au site AlwaysData, aller dans Accès Distant puis créer son utilisateur SSH avec un mot de passe. Une fois créé, nous pouvons accéder au lien "ssh-<nom_d'utilisateur>.alwaysdata.net" et tester si l'utilisateur créé fonctionne.
- Se connecter à votre espace dédié sur le serveur via ce protocole. Quelle est la ligne de commande nécessaire pour y arriver ? 

        La ligne de code est la suivante :                                                       $ ssh <nom_du_compte_alwaysdata>@ssh-<nom_d'utilisateur_SSH>.alwaysdata.net

- Dans quel repertoire faut-il déposer vos fichiers du site si vous voulez le voir en ligne ? (chemin complet sur le serveur) 

        Pour voir nos fichiers déposés sur le site, il faut aller dans le répertoire Home. Voici son chemin : /home/"nom_du_compte_alwaysdata"

## Etape 2 : Copier notre contenu sur Alwaysdata

Ajouter les fichiers du site sauvegardé en local au répertoire distant dédié.

- Quel est le chemin local absolu pour accéder à votre site ?

        Le chemin pour accéder à mon site est le suivant :                                       C:/Users/MoPiM/Desktop/portfolio_/og_dylan_portfolio/index.html
- Quel est le chemin absolu du repertoire dédié sur le serveur Alwaysdata ?

        Le chemin du répertoire dédié à mon site sur le serveur est le suivant :                /home/dylan/sites
- Les commandes `scp` et `rsync` peuvent être d'une grande aide à cette étape. Pourquoi ? 

        Les deux commandes servent à transférer des données en utilisant le protocole SSH. Nous devrons donc les utiliser si nous voulons ajouter les fichiers de notre site sur le répertoire distant.
- Quelle est la différence entre les deux commandes ?

        La différence entre les deux se situe dans leur manière de gérer le transfert des fichiers. scp est utilisé pour transférer des fichiers individuels ou des répertoires entiers de manière sécurisée, tandis que rsync est plus efficace pour la synchronisation de répertoires complets en ne transférant que les différences entre les fichiers source et de destination
- Quelle est la commande complète pour ajouter les fichiers sauvegardés en local sur le serveur dédié ?

        la commande complète pour ajouter les fichiers sauvegardés en local sur le serveur dédié est la suivante : $ scp chemin/du/fichier/fichier.txt <nom_du_compte_alwaysdata>@ssh-<nom_d'utilisateur_SSH>.alwaysdata.net:/home/<nom_du_compte_alwaysdata>/

- Comment vérifier que l'ajout a bien été effectué ? Détailler la procédure et les résultats attendus.

        Afin de vérifier que l'ajout a bien été effectué, il suffit d'accéder à l'interface ssh du serveur distant et de faire un "ls" pour vérifier les fichiers présents.
- Quelle URL permet de voir votre site en ligne ? 
