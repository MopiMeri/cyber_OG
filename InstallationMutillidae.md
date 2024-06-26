![bannière TP](imagesIM/bannieremutillidae.png)
ESIEE-IT - (BTS SIO SLAM) - 13/06/2024

---

![bannière 1](imagesIM/présentationmutillidae.png)

<span style="font-family: Consolas;font-size:18px">Mutillidae est un site web développé par OWASP pour identifier et tester les failles de sécurité. Ce projet open-source est conçu pour fournir une plateforme d'apprentissage pratique où les testeurs peuvent se familiariser avec les vulnérabilités courantes des applications web. En simulant un environnement réel contenant diverses failles de sécurité, Mutillidae permet aux utilisateurs de pratiquer l'exploitation de ces vulnérabilités et d'apprendre à les corriger.</span>

---

![bannière 2](imagesIM/installation.png)

### 📜 <span style="font-family: Consolas;font-size:25px">**Comment installer Mutillidae sur AlwaysData ?**</span>

<span style="font-family: Consolas;font-size:18px">Voici les étapes à suivre pour installer Mutillidae :</span>

<span style="font-family: Consolas;font-size:15px">1. Se connecter au serveur ssh de notre espace AlwaysData avec cette commande :</span>

>`ssh <nom_du_compte_alwaysdata>@ssh-<nom_de_l'utilisateur_ssh>.alwaysdata.net`

<span style="font-family: Consolas;font-size:15px">Voici l'exemple dans mon cas :</span>

 >`ssh dylan@ssh-dylan.alwaysdata.net`

<span style="font-family: Consolas;font-size:15px">2. On se positionne dans le répertoire **www** à l'aide de `cd www` et on écrit la commande suivante qui servira à importer mutillidae :</span>

>`git clone https://github.com/webpwnized/mutillidae.git`

![gifclone](imagesIM/gifclone.gif)

<span style="font-family: Consolas;font-size:15px">3. On se positionne dans le répertoire **src** à l'aide de `cd mutillidae/src` et on renomme le fichier .htaccess. Cela va nous donner l'accès à l'environnement propice à l'apprentissage des vulnérabilités et des techniques d'exploitation. Voici la commande à écrire :</span>

>`mv .htaccess no.htaccess`

### 📜 <span style="font-family: Consolas;font-size:25px">**Configuration de la base de données MySQL pour Mutillidae**</span>

<span style="font-family: Consolas;font-size:15px">Après avoir renommé le fichier .htaccess, vous devez configurer la base de données MySQL pour que Mutillidae fonctionne correctement. Voici les étapes à suivre :</span>

<span style="font-family: Consolas;font-size:15px">1. Créer une base de données MySQL dédiée :</span>

- Connectez-vous à l'interface de gestion MySQL d'AlwaysData.

    ![sql](imagesIM/mysql.png)

- Créez une nouvelle base de données. Par exemple, nommez-la "user"_mutillidae.

    ![bdd](imagesIM/bddcreate.png)

<span style="font-family: Consolas;font-size:15px">2. Ajouter un utilisateur MySQL dédié :</span>

- Toujours dans l'interface de gestion MySQL, ajoutez un nouvel utilisateur avec tous les droits sur la base de données user_mutillidae. Par exemple, utilisez user_mutilliuser comme nom d'utilisateur et mutillipwd comme mot de passe.

    ![user](imagesIM/user.png)

<span style="font-family: Consolas;font-size:15px">3. Modifier le fichier de configuration de la base de données :</span>

- Localisez le fichier database-config.inc dans le répertoire mutillidae/src/includes.

- Ouvrez le fichier et mettez à jour les informations de connexion à la base de données avec les détails de votre base de données et de l'utilisateur créés précédemment.

    ![database](imagesIM/databaseconfig.png)
     <span style="color: yellow">il manque un i dans le password...</span>

<span style="font-family: Consolas;font-size:15px">4. Initialiser la base de données :</span>

- Cliquez sur le lien proposé pour reconstruire la base de données.

    ![lien](imagesIM/lien.png)

- Acceptez la pop-up

    ![popup](imagesIM/popup.png)
    
- Vous voilà arrivé à la fin de l'installation.

    ![final](imagesIM/mutillidaeconfiguré.png)

### <span style="color: red">Attention, n'oubliez pas de renommer votre fichier `no.htaccess` en enlevant le `no`</span>

<span style="font-family: Consolas;font-size:15px">Pour cela, on se positionne dans le répertoire **src** à l'aide de `cd mutillidae/src` et on exécute la commande suivante :</span>

    mv no.htaccess .htaccess