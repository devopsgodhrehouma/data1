# 1 - Théorie: 
### 1. Introduction à Linux
- **Qu'est-ce que Linux ?** Brève histoire et pourquoi il est largement utilisé.
- **Distributions populaires :** Ubuntu, Fedora, CentOS, et Debian.

### 2. Premiers Pas
- **Accéder au terminal :** Expliquer comment ouvrir un terminal dans différentes distributions.
- **Structure des répertoires :** Description du système de fichiers Linux (`/`, `/home`, `/etc`, `/var`, etc.).

### 3. Commandes de Base
- **`pwd` :** Affiche le répertoire de travail actuel.
- **`ls` :** Liste les fichiers et dossiers dans le répertoire courant. Variantes utiles : `ls -l`, `ls -a`.
- **`cd` :** Change le répertoire courant (ex: `cd /home`).

### 4. Gestion des Fichiers et Dossiers
- **`mkdir` :** Créer un nouveau dossier (ex: `mkdir nouveau_dossier`).
- **`rmdir` / `rm` :** Supprimer un dossier vide (`rmdir`) ou des fichiers et dossiers non vides (`rm -r`).
- **`touch` :** Crée un nouveau fichier vide ou met à jour la date de modification d'un fichier existant.
- **`cp` :** Copier des fichiers et dossiers (ex: `cp fichier_origine fichier_destination`).
- **`mv` :** Déplacer ou renommer des fichiers et dossiers.

### 5. Gestion des Permissions
- **`chmod` :** Modifier les permissions d'un fichier ou dossier (ex: `chmod 755 fichier`).
- **`chown` :** Changer le propriétaire d'un fichier (ex: `chown utilisateur fichier`).

### 6. Gestion des Processus
- **`ps` :** Afficher les processus en cours.
- **`top` :** Afficher les processus et l'utilisation des ressources en temps réel.
- **`kill` :** Terminer un processus spécifique par son ID (ex: `kill 1234`).

### 7. Recherche de Fichiers
- **`find` :** Rechercher des fichiers et dossiers (ex: `find / -name "monfichier.txt"`).
- **`grep` :** Rechercher du texte dans des fichiers (ex: `grep "texte_recherché" fichier`).

### 8. Installation de Logiciels
- **`apt` (Debian, Ubuntu) :** Installer, mettre à jour et supprimer des logiciels (ex: `sudo apt install nom_paquet`).
- **`yum` (CentOS) / `dnf` (Fedora) :** Commandes équivalentes pour ces distributions.

### 9. Redirection et Pipelining
- **Redirections :** Utiliser `>`, `>>`, ou `<` pour diriger l'entrée et la sortie des commandes.
- **Pipelines :** Utiliser `|` pour passer la sortie d'une commande à une autre (ex: `ls -l | grep "txt"`).

### 10. Conclusion et Ressources Supplémentaires
- **Résumé des commandes :** Récapitulatif des commandes traitées.
- **Ressources en ligne :** Liens vers des ressources supplémentaires pour approfondir.

Ce tutoriel permettra aux débutants de se familiariser progressivement avec l'environnement Linux et ses commandes les plus courantes.

Bien sûr ! Voici quelques exercices pratiques pour permettre aux utilisateurs de tester leurs connaissances et de renforcer leur compréhension des commandes Linux de base. Ces exercices seront ajoutés à la fin du tutoriel pour offrir une application concrète des concepts appris.

# 2 - Exercices Pratiques

#### Exercice 1 : Navigation et Exploration
1. Ouvrez un terminal.
2. Utilisez la commande `pwd` pour afficher votre répertoire de travail actuel.
3. Naviguez dans le répertoire `/var/log`.
4. Listez tous les fichiers et dossiers dans ce répertoire, y compris les fichiers cachés.

#### Exercice 2 : Gestion de Fichiers
1. Créez un nouveau dossier nommé `TestLinux` dans votre répertoire personnel.
2. À l'intérieur de `TestLinux`, créez un fichier vide nommé `test.txt`.
3. Copiez `test.txt` dans un nouveau fichier appelé `test_backup.txt` dans le même répertoire.
4. Supprimez `test_backup.txt` en utilisant la commande appropriée.

#### Exercice 3 : Manipulation de Contenu
1. À l'intérieur du dossier `TestLinux`, créez un nouveau fichier `liste.txt` et ajoutez-y les noms de trois logiciels que vous utilisez fréquemment.
2. Utilisez `grep` pour trouver et afficher la ligne contenant le mot "logiciel" dans `liste.txt`.
3. Redirigez la sortie de `ls -l` dans un nouveau fichier appelé `details.txt` dans le dossier `TestLinux`.

#### Exercice 4 : Permissions et Propriété
1. Changez les permissions du fichier `liste.txt` pour permettre à tous les utilisateurs de le lire et de l'écrire.
2. Affichez les permissions de `liste.txt` pour vérifier le changement.
3. Changez le propriétaire de `liste.txt` à un autre utilisateur de votre système (remarque : cela peut nécessiter des droits d'administrateur).

#### Exercice 5 : Gestion des Processus
1. Ouvrez deux terminaux.
2. Dans le premier terminal, lancez la commande `top`.
3. Identifiez l'ID du processus pour la commande `top`.
4. Dans le deuxième terminal, utilisez la commande `kill` pour arrêter le processus `top` que vous avez lancé.

#### Exercice 6 : Recherche Avancée
1. Utilisez la commande `find` pour rechercher tous les fichiers se terminant par `.log` dans `/var/log`.
2. Combinez `find` avec `grep` pour rechercher tous les fichiers contenant le mot "error".

### Conclusion des Exercices
Ces exercices vous aideront à pratiquer et à mieux comprendre comment interagir avec le système d'exploitation Linux à travers le terminal. Ils renforcent votre capacité à manipuler des fichiers, gérer des processus, et modifier des permissions de manière efficace et sécurisée.

Ces exercices peuvent être ajustés en fonction du niveau de difficulté souhaité et peuvent également être utilisés comme devoirs ou évaluations pratiques dans un cadre éducatif.
