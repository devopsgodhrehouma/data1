# Gestion des Permissions sous Linux

Ce projet explique comment gérer les permissions des fichiers et des dossiers sous les systèmes d'exploitation Linux, comme Ubuntu et CentOS. Il vise à aider les utilisateurs à comprendre et à manipuler les permissions pour sécuriser leurs systèmes.

## Prérequis

Pour suivre ce tutoriel, vous aurez besoin d'avoir accès à une machine Linux, soit en local soit sur un serveur. Les distributions recommandées pour ce guide sont Ubuntu et CentOS.

## Installation

Aucune installation spécifique n'est nécessaire pour exécuter les commandes de base de Linux utilisées dans ce projet. Toutefois, assurez-vous que votre système est à jour :

```bash
sudo apt update && sudo apt upgrade  # Pour Ubuntu
sudo yum update                      # Pour CentOS
```

## Usage

### Vérifier les Permissions Actuelles

Pour vérifier les permissions d'un fichier ou d'un dossier, utilisez la commande `ls` avec l'option `-l` :

```bash
ls -l /chemin/vers/le/fichier
```

### Modifier les Permissions

Pour modifier les permissions d'un fichier, utilisez la commande `chmod`. Par exemple, pour donner au propriétaire le droit de lire, écrire, et exécuter le fichier :

```bash
chmod 700 /chemin/vers/le/fichier
```

### Changer le Propriétaire ou le Groupe

Pour changer le propriétaire d'un fichier :

```bash
sudo chown nouveau_proprietaire /chemin/vers/le/fichier
```

Pour changer le groupe d'un fichier :

```bash
sudo chown :nouveau_groupe /chemin/vers/le/fichier
```

# 2 - Exercices

D'accord, créons des exercices qui utilisent différentes permissions (`chmod 400`, `600`, `500`, `700`) pour donner aux utilisateurs la possibilité de pratiquer la modification des permissions de fichiers sur Linux. Chaque exercice présentera un scénario différent nécessitant l'application d'une de ces commandes pour modifier les permissions.

### Exercices Pratiques avec `chmod`

#### Exercice 1 : Lecture Seule pour le Propriétaire
**Scénario :** Vous avez un fichier important nommé `document_important.txt`. Vous voulez vous assurer que seul le propriétaire peut lire ce fichier, et que personne d'autre, y compris le groupe et les autres utilisateurs, ne puisse y accéder.

**Commande à utiliser :** `chmod 400 document_important.txt`

**Questions :**
1. Quel est l'effet de cette commande sur les permissions du fichier?
2. Comment vérifieriez-vous que les permissions ont été correctement mises à jour?

#### Exercice 2 : Lecture et Écriture pour le Propriétaire
**Scénario :** Vous travaillez sur un script appelé `script_de_travail.sh`. Vous voulez vous assurer que vous pouvez lire et écrire dans ce fichier, mais que personne d'autre, ni le groupe ni les autres utilisateurs, ne puisse voir ou modifier ce fichier.

**Commande à utiliser :** `chmod 600 script_de_travail.sh`

**Questions :**
1. Quelles permissions ce fichier a-t-il maintenant?
2. Pourquoi est-il important de limiter l'accès aux scripts contenant du code potentiellement sensible?

#### Exercice 3 : Exécution et Lecture pour le Propriétaire
**Scénario :** Vous avez un script `executer_script.sh` que vous souhaitez pouvoir lire et exécuter, mais pas modifier. Vous souhaitez également empêcher tout accès par les autres utilisateurs et le groupe.

**Commande à utiliser :** `chmod 500 executer_script.sh`

**Questions :**
1. Décrivez comment les permissions sont définies maintenant pour ce fichier.
2. Quelle serait une situation où ce type de permission serait particulièrement utile?

#### Exercice 4 : Permissions Complètes pour le Propriétaire
**Scénario :** Vous développez une application temporaire dans un fichier nommé `developpement_app.sh`. Vous voulez avoir toutes les permissions sur ce fichier pendant que vous travaillez dessus, mais vous ne voulez pas que les autres utilisateurs ou le groupe puissent interagir avec ce fichier.

**Commande à utiliser :** `chmod 700 developpement_app.sh`

**Questions :**
1. Expliquez les permissions attribuées à ce fichier après l'exécution de la commande.
2. Dans quel cas utiliseriez-vous cette commande pour un fichier ou script?


#### Exercice 5 : Tableau des Exercices sur les Permissions avec `chmod`

| No. | Commande                  | Scénario                                                                                         | Question                                                              |
|-----|---------------------------|--------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| 1   | `chmod 400 fichier.txt`   | Vous voulez que le fichier soit en lecture seule pour le propriétaire.                          | Quelles sont les permissions de `fichier.txt` après cette commande? |
| 2   | `chmod 600 script.sh`     | Le fichier script doit être accessible en lecture et écriture par le propriétaire uniquement.   | Décrivez les permissions de `script.sh`.                             |
| 3   | `chmod 500 backup.sh`     | Le script de sauvegarde doit être exécutable et lisible par le propriétaire mais pas modifiable.| Quelles permissions `backup.sh` possède-t-il maintenant?            |
| 4   | `chmod 700 mon_app.py`    | Vous travaillez sur une application et vous souhaitez des droits complets sur ce fichier.       | Quels sont les droits d'accès pour `mon_app.py`?                     |

### Instructions pour les Étudiants
Pour chaque scénario dans le tableau, indiquez les permissions exactes du fichier après l'application de la commande `chmod`. Vous devez préciser les droits pour le propriétaire, le groupe, et les autres utilisateurs en termes de lecture (r), écriture (w), et exécution (x).

- **Lecture (r)** : Permet de voir le contenu du fichier.
- **Écriture (w)** : Permet de modifier le contenu du fichier.
- **Exécution (x)** : Permet d'exécuter le fichier comme un programme.

### Exemple de Réponse
Pour la commande `chmod 400 fichier.txt` :
- **Propriétaire :** Lecture (r)
- **Groupe :** Aucun droit
- **Autres :** Aucun droit



#### Exercice 6 : Installer Apache2 et Configurer le Groupe

#### Étape 1: Installation d'Apache2
Ouvrez un terminal et exécutez la commande suivante pour installer Apache2 :

```bash
sudo apt update
sudo apt install apache2
```

#### Étape 2: Démarrer et Activer Apache2
Pour s'assurer qu'Apache2 fonctionne et qu'il démarre automatiquement au démarrage, exécutez :

```bash
sudo systemctl start apache2
sudo systemctl enable apache2
```

#### Étape 3: Modifier le Propriétaire et le Groupe des Fichiers Apache
Par défaut, Apache crée un dossier `www` dans `/var/www/html`. Pour changer le propriétaire et le groupe à `www-data` (l'utilisateur et le groupe standard pour Apache sur Ubuntu), utilisez :

```bash
sudo chown -R www-data:www-data /var/www/html
```

### Exercice Pratique 

#### Contexte
Vous avez installé Apache2 sur une machine Ubuntu pour votre projet de développement web. Pour des raisons de sécurité, vous devez vous assurer que le serveur web ne peut exécuter que les fichiers nécessaires et que ces fichiers sont propriété de l'utilisateur `www-data`.

#### Consigne
1. **Vérifier le Propriétaire Actuel :**
   - Utilisez la commande `ls -l /var/www/html` pour afficher les détails du propriétaire actuel des fichiers dans le dossier Apache.
   
2. **Modifier les Permissions :**
   - Changez les permissions du dossier `/var/www/html` pour que seul l'utilisateur `www-data` puisse lire, écrire et exécuter les fichiers, tandis que le groupe `www-data` ne peut que lire et exécuter les fichiers. Aucun autre utilisateur ne doit avoir accès à ce dossier.
   - Commande suggérée : `sudo chmod 750 /var/www/html`

3. **Question de Réflexion :**
   - Pourquoi est-il important de restreindre les permissions du dossier web à l'utilisateur `www-data`? Quels risques sont associés à des permissions trop permissives?


#### Exercice 7 : Installer httpd (Apache2) et Configurer le Groupe sur CentOS

#### Étape 1: Installation de httpd
Ouvrez un terminal et exécutez la commande suivante pour installer httpd :

```bash
sudo yum update
sudo yum install httpd
```

#### Étape 2: Démarrer et Activer httpd
Pour s'assurer que httpd fonctionne et qu'il démarre automatiquement au démarrage, exécutez :

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
```

#### Étape 3: Modifier le Propriétaire et le Groupe des Fichiers Apache
Par défaut, Apache crée un dossier `www` dans `/var/www/html`. Pour changer le propriétaire et le groupe à `apache` (l'utilisateur et le groupe standard pour Apache sur CentOS), utilisez :

```bash
sudo chown -R apache:apache /var/www/html
```

### Exercice Pratique 

#### Contexte
Vous avez installé httpd sur une machine CentOS pour votre projet de développement web. Pour des raisons de sécurité, vous devez vous assurer que le serveur web ne peut exécuter que les fichiers nécessaires et que ces fichiers sont propriété de l'utilisateur `apache`.

#### Consigne
1. **Vérifier le Propriétaire Actuel :**
   - Utilisez la commande `ls -l /var/www/html` pour afficher les détails du propriétaire actuel des fichiers dans le dossier Apache.
   
2. **Modifier les Permissions :**
   - Changez les permissions du dossier `/var/www/html` pour que seul l'utilisateur `apache` puisse lire, écrire et exécuter les fichiers, tandis que le groupe `apache` ne peut que lire et exécuter les fichiers. Aucun autre utilisateur ne doit avoir accès à ce dossier.
   - Commande suggérée : `sudo chmod 750 /var/www/html`

3. **Question de Réflexion :**
   - Pourquoi est-il important de restreindre les permissions du dossier web à l'utilisateur `apache`? Quels risques sont associés à des permissions trop permissives?

