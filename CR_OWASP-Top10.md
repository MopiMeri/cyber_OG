## Compte rendu du TOP 10 des failles de sécurité - OWASP
 [Dylan OG](mailto:dylan.og@edu.esiee-it.fr), ESIEE-IT, BTS-SIO, 15/05/2024


## **10 - Server-Side Request Forgery (SSRF)**

La Server-Side Request Forgery est une faille de sécurité où les applications web effectuent des requêtes non validées vers des ressources distantes, ouvrant la porte à des attaques malveillantes.

### Recommandations de l'OWASP pour la prévention

- Séparez l'accès aux ressources distantes dans des réseaux distincts pour minimiser l'impact potentiel de la SSRF.
- Effectuez une validation rigoureuse des entrées utilisateur pour éviter les URL malveillantes.
- Désactivez les fonctionnalités potentiellement risquées comme les redirections HTTP.

### Implication des développeurs

En tant que développeurs, nous devons intégrer ces pratiques dès la conception des applications pour garantir leur sécurité contre cette menace potentielle.

## **9 - Security Logging and Monitoring Failures**

La Broken Access Control se produit lorsque les politiques de contrôle d'accès sont mal appliquées, permettant aux utilisateurs d'accéder à des données ou des fonctionnalités auxquelles ils ne devraient pas avoir accès.

### Recommandations de l'OWASP pour la prévention

- S'assurer que les échecs de connexion, de contrôle d'accès et de validation des entrées côté serveur sont correctement enregistrés pour une analyse ultérieure.
- Encoder correctement les données de journalisation pour éviter les injections ou les attaques sur les systèmes de journalisation.
- Mettre en place un journal d'audit pour les transactions à haute valeur ajoutée avec des contrôles d'intégrité.
- Mettre en place des systèmes d'alertes et de surveillance efficaces pour détecter rapidement les activités suspectes.

### Implication des développeurs

En tant que développeurs, nous devons enregistrer correctement les échecs de connexion et en mettre en place des mécanismes de surveillance efficaces pour détecter les activités suspectes.

## **8 - Software and Data Integrity Failures**

Les Software and Data Integrity Failures surviennent lorsque le code et l'infrastructure ne sont pas suffisamment sécurisés pour empêcher les atteintes à l'intégrité, telles que l'utilisation de plugins ou de mises à jour non vérifiées, ce qui expose les systèmes à des risques potentiels de compromission ou d'exécution de code malveillant.

### Recommandations de l'OWASP pour la prévention

- Utiliser des signatures numériques ou des mécanismes similaires pour vérifier que le logiciel ou les données proviennent de la source attendue et n'ont pas été altérés.

- S'assurer que les bibliothèques et les dépendances, telles que npm ou Maven, proviennent de référentiels de confiance. Pour un profil de risque plus élevé, envisager d'héberger un référentiel interne connu comme étant sûr et validé.

- Utiliser un outil de sécurité de la chaîne logicielle, tel que OWASP Dependency Check ou OWASP CycloneDX, pour vérifier que les composants ne contiennent pas de vulnérabilités connues.

- Mettre en place un processus de révision pour les changements de code et de configuration afin de réduire les risques d'introduction de code ou de configuration malveillants dans votre pipeline logiciel.

- Assurer que votre pipeline CI/CD dispose d'une bonne ségrégation, configuration et contrôle d'accès pour garantir l'intégrité du code circulant à travers les processus de construction et de déploiement.

- Veiller à ce que les données sérialisées non signées ou non chiffrées ne soient pas envoyées à des clients non fiables sans une forme de vérification d'intégrité ou de signature numérique pour détecter toute altération ou rejeu des données sérialisées.

### Implication des développeurs

En tant que développeurs, nous devons nous assurer que les logiciels que nous créons vérifient l'origine et l'intégrité des données et des mises à jour. Nous devons également utiliser des bibliothèques sûres, intégrer des outils de sécurité et suivre des processus de révision rigoureux pour détecter et corriger les vulnérabilités, contribuant ainsi à protéger les applications que nous développons contre les attaques malveillantes.

## **7 - Identification and Authentication Failures**

Les Identification and Authentication Failures se produisent quand les systèmes informatiques ne vérifient pas correctement qui sont les utilisateurs ou comment ils se connectent, ce qui peut rendre les données vulnérables et permettre des accès non autorisés.

### Recommandations de l'OWASP pour la prévention

- Utiliser l'authentification multi-facteurs pour renforcer la sécurité.
  
- Éviter d'utiliser des identifiants par défaut pour les utilisateurs, surtout pour les administrateurs.

- Vérifier les mots de passe faibles et les empêcher d'être utilisés.

- Suivre les directives de sécurité des mots de passe, telles que celles du NIST 800-63.

- Renforcer les processus d'enregistrement et de récupération des identifiants pour éviter les attaques d'énumération de comptes.

- Limiter les tentatives de connexion infructueuses pour prévenir les attaques par force brute.

- Utiliser un gestionnaire de session sécurisé côté serveur pour protéger les sessions utilisateur.

### Implication des développeurs

En tant que développeurs,  nous devons intégrer des méthodes de vérification multi-facteurs, éviter les identifiants par défaut et de renforcer la sécurité des mots de passe utilisés dans nos applications.

## **6 - Vulnerable and Outdated Components**

Les "Vulnerable and Outdated Components" sont des parties de logiciels dans une application qui sont vulnérables ou obsolètes en raison de leur manque de mises à jour pour corriger les failles de sécurité.

### Recommandations de l'OWASP pour la prévention

- Mettre en place un processus de gestion des correctifs pour supprimer les dépendances inutilisées et continuellement surveiller les versions des composants.

- Utiliser des outils de vérification des vulnérabilités pour scanner régulièrement les composants utilisés et s'abonner aux bulletins de sécurité.

- Obtenir les composants uniquement à partir de sources officielles et sécurisées, en privilégiant les packages signés pour réduire les risques d'inclure des composants malveillants.

- Surveiller les composants non maintenus et déployer des correctifs virtuels si nécessaire.

### Implication des développeurs

En tant que développeurs, nous devons nous assurer que nos logiciels soient régulièrement mis à jour pour éviter les vulnérabilités de sécurité.

## **5 - Security Misconfiguration**

La "Security Misconfiguration" fait référence à des erreurs de configuration de sécurité dans une application ou sur un serveur qui peuvent rendre celle-ci vulnérable aux attaques. Cela peut inclure des paramètres de sécurité mal configurés, des fonctionnalités inutiles activées, des comptes par défaut non sécurisés, ou encore l'exposition d'informations sensibles via des messages d'erreur.

### Recommandations de l'OWASP pour la prévention

- Mettre en place un processus d'installation sécurisé, incluant une procédure de durcissement répétable pour déployer rapidement des environnements sécurisés identiques sur tous les niveaux (développement, QA, production).

- Installer une plateforme minimale sans fonctionnalités inutiles, en supprimant ou en n'installant pas les fonctionnalités et frameworks non utilisés.

- Réviser et mettre à jour les configurations en fonction des correctifs de sécurité et des mises à jour, en incluant une revue des permissions de stockage cloud.

- Mettre en place une architecture d'application segmentée pour assurer une séparation efficace et sécurisée entre les composants ou les utilisateurs, en utilisant la segmentation, la conteneurisation ou les groupes de sécurité cloud.

- Envoyer des directives de sécurité aux clients, par exemple en utilisant des en-têtes de sécurité.

- Automatiser le processus de vérification de l'efficacité des configurations dans tous les environnements.

### Implication des développeurs

En tant que développeurs, nous devons être attentifs à la configuration de sécurité de nos applications pour éviter les vulnérabilités. 

## **4 - Insecure Design**

L'Insecure Design se réfère à des défauts de conception dans les logiciels ou systèmes qui les rendent vulnérables aux attaques. Ces faiblesses résultent souvent d'une planification insuffisante des mesures de sécurité, telles que l'absence de modélisation des menaces ou de conception sécurisée.

### Recommandations de l'OWASP pour la prévention

- Établir et utiliser un cycle de développement sécurisé avec des professionnels de la sécurité des applications pour évaluer et concevoir des contrôles de sécurité et de confidentialité.
- Mettre en place et utiliser une bibliothèque de motifs de conception sécurisés ou de composants prêts à l'emploi.
- Utiliser la modélisation des menaces pour les processus d'authentification critiques, le contrôle d'accès, la logique métier et les flux clés.
- Intégrer le langage et les contrôles de sécurité dans les histoires utilisateur.
- Intégrer des vérifications de plausibilité à chaque niveau de votre application (du front-end au back-end).
- Rédiger des tests unitaires et d'intégration pour valider que tous les flux critiques sont résistants au modèle de menace. Compiler des cas d'utilisation et des cas d'utilisation détournés pour chaque niveau de votre application.
- Séparer les couches de tiers sur les couches système et réseau en fonction de l'exposition et des besoins de protection.
- Séparer de manière robuste les locataires à travers toutes les couches.
- Limiter la consommation de ressources par utilisateur ou service.

### Implication des développeurs

En tant que développeurs, nous sommes concernés par la conception sécuritaire de nos applications, en intégrant les contrôles de sécurité dès le début du processus de développement. Nous devons utiliser des cycles de développement sécurisés, intégrer des tests de sécurité tout au long du processus, suivre des modèles de conception sécurisés et tenir compte des besoins de protection des données et des ressources.


## **3 - Injection**

L'injection se produit lorsqu'une application n'effectue pas de validation, de filtrage ou de désinfection des données fournies par l'utilisateur, permettant ainsi à des données hostiles d'être exécutées comme des commandes ou des requêtes dans l'interpréteur de l'application.

### Recommandations de l'OWASP pour la prévention

- Utilisez de préférence une API sécurisée qui évite complètement l'utilisation de l'interpréteur, fournit une interface paramétrée ou migre vers des outils de mappage objet-relationnel (ORM).
- Utilisez une validation positive des entrées côté serveur. Ce n'est pas une défense complète car denombreuses applications nécessitent des caractères spéciaux, tels que les zones de texte ou les API pourles applications mobiles.
- Pour toute requête dynamique résiduelle, échappez les caractères spéciaux à l'aide de la syntaxed'échappement spécifique à cet interpréteur.
- Utilisez LIMIT et d'autres contrôles SQL dans les requêtes pour empêcher la divulgation massived'enregistrements en cas d'injection SQL.

### Implication des développeurs

Les développeurs peuvent prendre des mesures telles que la validation rigoureuse des données utilisateur, l'utilisation de requêtes paramétrées et d'API sécurisées, ainsi que l'utilisation d'outils de test de sécurité des applications pour identifier et corriger les vulnérabilités d'injection dans leur code.

## **2 - Cryptographic Failures**

Les "Cryptographic Failures" désignent les erreurs liées à l'utilisation incorrecte ou inefficace de techniques de cryptographie pour protéger les données sensibles, ce qui peut conduire à des expositions non autorisées de ces données.

### Recommandations de l'OWASP pour la prévention

- Identifiez les données sensibles selon les lois sur la confidentialité, les exigences réglementaires ou les besoins commerciaux.
- Évitez de stocker des données sensibles plus longtemps que nécessaire ou utilisez des méthodes de tokenisation ou de troncation conformes à la norme PCI DSS.
- Assurez-vous de chiffrer toutes les données sensibles au repos.
- Utilisez des algorithmes, protocoles et clés forts et à jour.
- Chiffrez toutes les données en transit avec des protocoles sécurisés tels que TLS.
- Mettez en place une gestion appropriée des clés.
- Stockez les mots de passe à l'aide de fonctions de hachage adaptatives et salées.
- Vérifiez indépendamment l'efficacité de la configuration et des paramètres.

### Implication des développeurs

Les développeurs doivent s'assurer que les données sensibles sont correctement classifiées et stockées uniquement aussi longtemps que nécessaire, en utilisant des méthodes de chiffrement adéquates pour protéger les données en transit et au repos. De plus, ils doivent mettre en place une gestion sécurisée des clés et effectuer une validation indépendante pour garantir l'efficacité des mesures de sécurité.

## **1 - Broken Access Control**

Broken Access Control se réfère à des failles qui surviennent lorsque les politiques de contrôle d'accès ne sont pas correctement appliquées, permettant aux utilisateurs de contourner les restrictions prévues et d'accéder à des données ou des fonctionnalités auxquelles ils ne devraient pas avoir accès.

### Recommandations de l'OWASP pour la prévention

- Mettre en œuvre des mécanismes de contrôle d'accès une fois et les réutiliser dans toute l'application, en minimisant l'utilisation du partage de ressources inter-origines (CORS).
- Les contrôles d'accès modélisés doivent appliquer la propriété des enregistrements plutôt que d'accepter que l'utilisateur puisse créer, lire, mettre à jour ou supprimer n'importe quel enregistrement.
- Les exigences de limite commerciale spécifiques de l'application doivent être appliquées par les modèles de domaine.
- Désactiver la liste des répertoires du serveur Web et s'assurer que les métadonnées de fichiers (par exemple, .git) et les fichiers de sauvegarde ne sont pas présents dans les racines Web.
- Journaliser les échecs de contrôle d'accès, alerter les administrateurs si nécessaire (par exemple, échecs répétés).
- Limiter le taux d'accès aux API et aux contrôleurs pour minimiser les dommages causés par les outils d'attaque automatisés.

### Implication des développeurs

En tant que développeur, nous sommes concernés par le "broken access control". Pour remédier à ce problème, nous pouvons mettre en œuvre des mécanismes de contrôle d'accès au niveau du serveur, appliquer le principe du déni par défaut, modéliser les contrôles d'accès pour appliquer la propriété des enregistrements, et mettre en place des tests unitaires et d'intégration fonctionnels pour valider le contrôle d'accès.
