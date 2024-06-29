# Introduction aux Commandes HDFS

Ce guide décrit les étapes nécessaires pour manipuler des fichiers dans Hadoop en utilisant HDFS (Hadoop Distributed File System). 

## Prérequis
- Accès à une distribution Hadoop (comme Cloudera)
- Connexion Internet pour télécharger des fichiers

## Étapes

### Étape 1: Ouvrir la ligne de commande
1. Effectuez un clic droit sur votre bureau et ouvrez la ligne de commande.

### Étape 2: Lister les fichiers dans le bureau local
```bash
[cloudera@quickstart Desktop]$ ls
```

### Étape 3: Lister les fichiers dans Hadoop
```bash
[cloudera@quickstart Desktop]$ hadoop fs -ls
```

### Étape 4: Créer ou télécharger un fichier test.csv
Créez un fichier `test.csv` d'une taille supérieure à 128 Mo sur votre bureau ou téléchargez-le simplement à partir de ce [lien](https://drive.google.com/drive/folders/1i1pqgpMRr5DhSJ-4rn5FfCe9H-8TpAFM?usp=sharing).

### Étape 5: Envoyer le fichier test.csv à Hadoop
Faites glisser et déposez le fichier `test.csv` dans le terminal pour copier le chemin du fichier, puis exécutez la commande suivante :
```bash
[cloudera@quickstart Desktop]$ hadoop fs -put '/home/cloudera/Desktop/test.csv'
```
Le fichier sera copié sous le nom de `test.csv` dans `/user/cloudera`. Pour vérifier l'existence du fichier, exécutez :
```bash
[cloudera@quickstart Desktop]$ hadoop fs -ls
```

### Étape 6: Renommer le fichier sur Hadoop
Si vous souhaitez nommer le fichier dans Hadoop `testHadoop.csv`, exécutez :
```bash
[cloudera@quickstart Desktop]$ hadoop fs -put '/home/cloudera/Desktop/test.csv' testHadoop.csv
```

### Étape 7: Lister les fichiers dans Hadoop
Pour lister l'ensemble des fichiers dans `/user/cloudera`, exécutez :
```bash
[cloudera@quickstart Desktop]$ hadoop fs -ls
```

### Étape 8: Vérifier la division physique des données
Pour vérifier la division physique des données en des blocs de taille de 128 Mo, ainsi que la taille de chaque bloc de données et la liste de blocs, exécutez :
```bash
[cloudera@quickstart Desktop]$ hdfs fsck /user/cloudera/test.csv -files -blocks -locations
```

### Méthode Alternative : Utilisation de l'Interface Hue
1. Connectez-vous à l'interface Hue.
2. Utilisez les informations de connexion suivantes :
   - **Nom d'utilisateur** : cloudera
   - **Mot de passe** : cloudera
3. Parcourez les fichiers que vous avez envoyés avec la commande `put`.

---

## Autres Commandes Utiles HDFS

### Copier des fichiers
- Copier un fichier local vers HDFS :
  ```bash
  hadoop fs -copyFromLocal /local/path /hdfs/path
  ```

- Copier un fichier dans HDFS vers le système de fichiers local :
  ```bash
  hadoop fs -copyToLocal /hdfs/path /local/path
  ```

### Supprimer des fichiers
- Supprimer un fichier dans HDFS :
  ```bash
  hadoop fs -rm /hdfs/path/filename
  ```

- Supprimer un répertoire et son contenu :
  ```bash
  hadoop fs -rm -r /hdfs/path/directory
  ```

### Créer des répertoires
- Créer un répertoire dans HDFS :
  ```bash
  hadoop fs -mkdir /hdfs/path/directory
  ```

### Consulter le contenu d'un fichier
- Afficher le contenu d'un fichier dans HDFS :
  ```bash
  hadoop fs -cat /hdfs/path/filename
  ```

- Afficher les premières lignes d'un fichier :
  ```bash
  hadoop fs -head /hdfs/path/filename
  ```

- Afficher les dernières lignes d'un fichier :
  ```bash
  hadoop fs -tail /hdfs/path/filename
  ```

### Consulter l'espace utilisé
- Afficher l'espace utilisé par un répertoire ou un fichier :
  ```bash
  hadoop fs -du -h /hdfs/path
  ```

### Déplacer et renommer des fichiers
- Déplacer ou renommer un fichier dans HDFS :
  ```bash
  hadoop fs -mv /hdfs/path/source /hdfs/path/destination
  ```

### Changer les permissions des fichiers
- Changer les permissions d'un fichier ou répertoire dans HDFS :
  ```bash
  hadoop fs -chmod 755 /hdfs/path/filename
  ```

- Changer le propriétaire d'un fichier ou répertoire :
  ```bash
  hadoop fs -chown user:group /hdfs/path/filename
  ```

### Voir les statistiques de répertoire
- Afficher les statistiques d'un répertoire dans HDFS :
  ```bash
  hadoop fs -stat /hdfs/path
  ```

### Compter les fichiers et répertoires
- Compter le nombre de fichiers et répertoires dans HDFS :
  ```bash
  hadoop fs -count /hdfs/path
  ```

### Voir les métadonnées des fichiers
- Afficher les informations détaillées d'un fichier dans HDFS :
  ```bash
  hadoop fs -stat '%n %b %o %r %y %g %u' /hdfs/path/filename
  ```

---

## Remarques

- Toutes les commandes doivent être exécutées depuis le terminal de votre distribution Hadoop.
- L'interface Hue peut être utilisée pour des opérations graphiques et vérifier le statut des fichiers dans HDFS.
- Assurez-vous que le fichier `test.csv` est bien présent sur votre bureau avant d'exécuter les commandes.

---

Ce guide vous aidera à commencer avec les commandes de base HDFS pour gérer vos fichiers dans Hadoop. N'hésitez pas à consulter la documentation officielle d'Hadoop pour plus de détails et de fonctionnalités avancées.
