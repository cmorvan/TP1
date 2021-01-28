# ![](ressources/logo.jpeg)

# Bases de la programmation orientée objet 

### IUT Montpellier-Sète – Département Informatique

* **Cours:** [M2103](http://cache.media.enseignementsup-recherche.gouv.fr/file/25/09/7/PPN_INFORMATIQUE_256097.pdf) - support [ici](https://github.com/IUTInfoMontp-M2103/Ressources)
* **Enseignants:** [Marin Bougeret](mailto:marin.bougeret@umontpellier.fr), [Romain Lebreton](mailto:romain.lebreton@umontpellier.fr), [Sophie Nabitz](mailto:sophie.nabitz@univ-avignon.fr), [Victor Poupet](mailto:victor.poupet@umontpellier.fr), [Petru Valicov](mailto:petru.valicov@umontpellier.fr)
* Le [forum Piazza](https://piazza.com/class/kjifrxy1n0i3xa) de ce cours pour poser vos questions
* [Email](mailto:petru.valicov@umontpellier.fr) pour une question d'ordre privée concernant le cours.

<!--Avant de démarrer le TP, vérifiez que vous n'avez pas atteint votre quota d'espace de stockage autorisé :

* placez-vous dans votre `$HOME` et utilisez les commandes suivantes :
    * `du -sh` pour voir combien d'espace vous avez déjà utilisé
    * `du -sh *` pour voir combien d'espace vous avez déjà utilisé pour chaque fichier (sans fichiers cachés)
    * `du -sch .[!.]* *` pour voir combien d'espace vous avez déjà utilisé pour chaque fichier, y compris les fichiers cachés
* Supprimez les fichiers inutiles.
* Pour évitez des problèmes durant vos TPs d'informatique, vous devriez toujours **garder 300-400 Mo d'espace libre**.
-->

Les instructions de ce TP et de ceux qui vont suivre sont destinés pour les utilisateurs Linux (Ubuntu ou autre). Nous vous encourageons d'utiliser Linux car pour plusieurs cours vous en aurez besoin plus tard et plus généralement en tant qu'informaticien, c'est important d'être familiarisé avec. 
Si tout de même vous préférez utiliser Windows ou Mac OS, une adaptation est possible, mais cela vous demandera un peu de travail de votre côté. Discutez-en avec votre chargé de TD avant de démarrer le TP !

## TP 1 : Rappels de Git et premier projet versionné

L'objectif de la première partie de ce TP est de vous rappeler les concepts principaux liés à la [gestion de version](https://fr.wikipedia.org/wiki/Gestion_de_versions) avec [Git](https://git-scm.com/). Cet outil vous sera indispensable durant l'apprentissage de ce cours mais également dans d'autres matières durant votre cursus. En effet, au delà de la **programmation orientée objets** (l'objectif pédagogique principal du cours), en tant que futur développeur, vous devriez apprendre à être organisé et à collaborer avec d'autres développeurs. <!-- Vous apprendrez également à ne pas réinventer la roue : l'informatique est aujourd'hui une science très riche, donc savoir se faire assister par des outils informatiques est essentiel. Pour beaucoup d'entre vous ce TP sera la première occasion de se confronter à l'utilisation d'un [IDE](https://fr.wikipedia.org/wiki/Environnement_de_d%C3%A9veloppement), aux [tests unitaires](https://fr.wikipedia.org/wiki/Test_unitaire) et à des outils de gestion de cycle de vie logiciel.-->

### Introduction à Git et préparation de l'environnement

Pour conserver vos réalisations et permettre à votre enseignant de suivre votre avancement vous allez apprendre à versionner votre travail avec Git sur la plateforme collaborative [GitHub](https://github.com/). Pendant ce module, vous allez principalement écrire du code pour vous-même et qui sera partagé avec vos enseignants. Lorsque vous allez travailler sur le projet de POO à plusieurs vous allez pouvoir mesurer tout le potentiel d'un gestionnaire de version. Car tout l'intérêt de travailler avec Git c'est de pouvoir __collaborer__ de manière organisée.

#### Création d'un compte Github

Rendez-vous sur la page d'accueil de [GitHub](https://github.com/) :

![](ressources/Github.png)

Cliquez sur _Sign Up_ et dans la page qui apparaît, inscrivez votre nom d'utilisateur. Celui-ci doit être **obligatoirement** composé de votre prénom et de votre nom séparé par le caractère '-'. Si un utilisateur avec ce nom existe déjà, ajoutez un chiffre à la fin pour éviter les doublons.
Dans le champ _Email Adress_ indiquez votre **adresse universitaire**. Attention : il est important que l'adresse soit universitaire afin de pouvoir bénéficier des avantages liés à votre statut d'étudiant. 

![](ressources/creation_compte.png)

Une fois le mot de passe renseigné, cliquez sur le bouton _Next: Select a plan_. Sur l'écran suivant, vous choisirez l'option de base (qui coûte 0 dollars). Le troisième et dernier écran d'enregistrement vous demande des informations sur votre profil. Indiquez que vous êtes un étudiant et que vous comptez utiliser GitHub pour des projets étudiants :

![](ressources/preferences.png)

Une fois ces informations renseignées vous pouvez cliquer sur _Complete Setup_ pour définitivement créer votre compte. N'oubliez pas de valider votre adresse email en allant cliquer sur le lien reçu dans votre boîte mail.

#### Paramétrage de votre compte GitHub

Maintenant que votre compte est créé, il faut personnaliser votre profil. GitHub, en plus de vous fournir un moyen simple 
et efficace de conserver votre code en ligne, est aussi un réseau social de développeurs. Pour que votre profil puisse 
être valorisé un jour dans votre carrière pro, vous devez correctement renseigner vos informations.

#### Demande du "Student Pack" (optionnel)

Si vous le souhaitez, vous pouvez demander une remise académique vous permettant de bénéficier de nombreux avantages : des licences gratuites pour différents logiciels, possibilité d'avoir un nombre illimité de collaborateurs sur un projet privé, des outils d'intégration continue etc. Pour obtenir la licence académique il faut vous rendre sur la page suivante : https://education.github.com/pack

Cliquez sur le bouton "Get your pack" et certifiez que vous êtes bien un étudiant. Vérifiez les informations vous concernant et validez le formulaire pour terminer cette demande. Généralement la validation de la demande intervient dans l'heure mais il peut arriver que ça prenne plus de temps donc pas d'inquiétude. Même si on vous conseille d'avoir le Student Pack, ce n'est pas obligatoire pour pouvoir réaliser les TPs.

#### Prise en main de Git

Git est installé sur les postes Linux du département informatique de l'IUT Montpellier-Sète. Voici comment l'installer sur votre machine en fonction de votre système d'exploitation :
* Ubuntu ou une Debian : `sudo apt install git-all`
* une autre distribution Linux : https://git-scm.com/download/linux
* Windows : https://desktop.github.com/ - application gratuite proposée par GitHub qui vous permet d'installer le logiciel Git sous Windows et aussi une interface graphique appropriée
* Mac OS : https://git-scm.com/download/mac

**Configuration locale de Git**

Si ce n'est pas déjà fait, configurez correctement Git sur votre machine. Pour faire cela sur Linux, ouvrez le fichier `~/.gitconfig` avec votre éditeur de texte favori et renseignez votre nom, prénom et email dans la section `[user]`.
```
# Personnalisez les champs ci-dessous!
[user]
username = choucroute-garnie
name = Choucroute Garnie
email = choucroute.garnie@etu.umontpellier.fr
```

Une autre façon de faire (qui marche sur tous les systèmes) :
```
git config --global user.name "Choucroute Garnie"
git config --global user.email choucroute.garnie@etu.umontpellier.fr
```

**Entraînez-vous avec le tutoriel interactif !**

Normalement, la plupart d'entre vous ont suivi au Semestre 1 le [tutoriel Git](https://gitlabinfo.iutmontp.univ-montp2.fr/valicov/tutoGit1ereAnnee) de l'IUT et cela vous sera utile dans le cours. Néanmoins vous devriez vous entraîner un peu plus, notamment sur l'utilisation des branches. On vous propose donc ici d'utiliser le tutoriel interactif **[Git-It](https://github.com/jlord/git-it-electron)**. 
C'est une application multi-plateforme qui contient des défis pour l'apprentissage, en utilisant vraiment Git et GitHub, pas des émulateurs. Ces défis sont à réaliser en ligne de commande et avec GitHub. À la fin, lorsque vous aurez terminé tous les défis, vous aurez de vrais dépôts sur votre compte GitHub avec vos contributions. Pour faire ce tutoriel :
  * Téléchargez le fichier **"Git-it-Linux-x64.zip"** (ou Mac, ou Windows) depuis ce site : https://github.com/jlord/git-it-electron/releases.
  * Décompressez-le dans votre répertoire principal (`$HOME` sur Linux) et lancez l'exécutable `Git-it`. Une interface en français plus ou moins bien traduite est également disponible... La première étape du tutoriel (sur la création d'un compte GitHub) peut être passée car vous l'avez déjà réalisée dans la précédente étape du TP.

Ultérieurement, lorsque vous aurez oublié tout ce que le tuto vous a appris, vous pourrez utiliser ce mini [document](https://pageperso.lis-lab.fr/~petru.valicov/Cours/archives/Aix/M2104/Demarrer%20avec%20Git) qui résume les fonctionnalités principales de Git.

### Création de votre fork du TP1
Vous allez pouvoir commencer à travailler sur vos TP. Désormais le rendu, l'évaluation et le suivi de votre travail passeront par GitHub. La première chose que vous allez donc faire est de créer un fork d'un dépôt. Mais **attention**, pour cela vous n'utiliserez pas le bouton _fork_ classique de GitHub mais vous cliquerez sur **[CE LIEN](https://classroom.github.com/a/u-MsinoI)** !

GitHub va vous créer un dépôt __IUTInfoMontp-M2103/tp1-votreUsername__ contenant le fork du __IUTInfoMontp-M2103/TP1__. Le dépôt nouvellement créé sera privé et vous apparaîtrez automatiquement comme contributeur de ce projet pour y pousser votre travail. Voici à quoi devrait rassembler l'entête de votre page GitHub en haut à gauche de la page (dans l'exemple le _username_ est _pvalicov_) :

![](ressources/Fork_avec_classroom.png)

Remarquez que ce fork privé sera automatiquement intégré dans l'organisation du cours : _IUTInfoMontp-M2103_. Ce qui implique que les enseignants du module seront automatiquement admins de votre dépôt et pourront collaborer avec vous. Cette façon de faire permet d'une part de centraliser et uniformiser les rendus de chaque étudiant et, d'autre part, aux enseignants de suivre et aider plus facilement chaque étudiant en interagissant directement sur son dépôt. Cela permet également de partager plus facilement une base de code et veiller au respect des consignes en y intégrant une batterie de tests. Mais cette dernière partie on la verra plus tard...

Vous allez cloner le fork GitHub '*IUTInfoMontp-M2103/tp1-votreUsername*' sur votre machine et travailler désormais localement tout en "versionnant" votre code et en poussant régulièrement vos réalisations.

### À faire pour chaque exercice 
Une fois qu'un exercice sera terminé, n'oubliez pas de pousser vos modifications sur votre fork de la manière suivante (dans cet exemple on suppose que vous êtes sur la branche master) :
```sh
~/tpPOO/tp1-VotreUsername$ git add fichiers_que_vous_avez_modifié
~/tpPOO/tp1-VotreUsername$ git commit -m "Validation de l'exercice 1"
~/tpPOO/tp1-VotreUsername$ git push origin master
```

**Remarque importante** : Rappelez-vous qu'un dépôt contient uniquement les fichiers nécessaires pour qu'un collaborateur puisse reconstruire le projet dans son propre environnement, et surtout _rien de plus_. Donc aucune information personnelle, aucun résultat de compilation, aucune configuration de son propre environnement de travail, ...

### Un petit Salut le Monde qui va bien !
#### Exercice 1
Dans la méthode principale de la classe `HelloWorld` faites afficher le message _"Salut le monde"_.
1. Dans un terminal, compilez, exécutez et vérifiez votre programme.
2. Versionnez l'intégralité de votre travail avec `git add .` + `git commit`.
3. Faites un `git push` sur le dépôt GitHub et comparez avec votre répertoire local. Quelle différence constatez-vous et pourquoi ?

En règle générale une séparation entre le code source et le byte code est nécessaire pour une meilleure lisibilité de votre programme. Ce qui est généralement conseillé c'est d'avoir au moins deux répertoires à la racine de votre projet. Par exemple `src` + `bin` ou encore `src` + `target`. Pour les différentes options de compilation : https://docs.oracle.com/javase/8/docs/technotes/tools/unix/javac.html
