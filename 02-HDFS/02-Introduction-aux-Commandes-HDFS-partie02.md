Voici un tutoriel révisé et enrichi des commandes HDFS, avec les modifications de noms demandées et l'ajout de nouvelles commandes pour offrir un laboratoire complet aux débutants :

### 1. Lister les fichiers et répertoires
- **Commande :** `hdfs dfs -ls <chemin>`
- **Exemple :** Pour lister tous les répertoires dans HDFS depuis le répertoire de travail `cloudera/Downloads` :
  ```bash
  hdfs dfs -ls /
  ```

### 2. Créer un répertoire
- **Commande :** `hdfs dfs -mkdir <chemin>`
- **Exemple :** Pour créer un répertoire nommé `haythem` dans HDFS :
  ```bash
  hdfs dfs -mkdir /haythem
  ```

### 3. Créer un fichier vide
- **Commande :** `hdfs dfs -touchz <chemin_fichier>`
- **Exemple :** Pour créer un fichier vide `monfichier.txt` dans le répertoire `haythem` :
  ```bash
  hdfs dfs -touchz /haythem/monfichier.txt
  ```

### 4. Copier des fichiers du système local vers HDFS
- **Commande :** `hdfs dfs -copyFromLocal <chemin_fichier_local> <chemin_hdfs>`
- **Exemple :** Pour copier un fichier `Rehouma.txt` du répertoire `Downloads` vers le répertoire `haythem` sur HDFS :
  ```bash
  hdfs dfs -copyFromLocal ~/Downloads/Rehouma.txt /haythem
  ```

### 5. Afficher le contenu d'un fichier
- **Commande :** `hdfs dfs -cat <chemin>`
- **Exemple :** Pour afficher le contenu du fichier `Rehouma.txt` situé dans le dossier `haythem` :
  ```bash
  hdfs dfs -cat /haythem/Rehouma.txt
  ```

### 6. Copier des fichiers d'HDFS vers le système local
- **Commande :** `hdfs dfs -copyToLocal <src_hdfs> <dest_local>`
- **Exemple :** Pour copier un fichier de `haythem` dans le répertoire local `Downloads` :
  ```bash
  hdfs dfs -copyToLocal /haythem/Rehouma.txt ~/Downloads/
  ```

### 7. Déplacer des fichiers du local vers HDFS
- **Commande :** `hdfs dfs -moveFromLocal <src_local> <dest_hdfs>`
- **Exemple :** Pour déplacer un fichier du dossier `Downloads` vers `haythem` sur HDFS :
  ```bash
  hdfs dfs -moveFromLocal ~/Downloads/fichieradeplacer.txt /haythem
  ```

### 8. Copier des fichiers au sein de HDFS
- **Commande :** `hdfs dfs -cp <src_hdfs> <dest_hdfs>`
- **Exemple :** Pour copier un dossier `haythem` vers `haythem_copie` :
  ```bash
  hdfs dfs -cp /haythem /haythem_copie
  ```

### 9. Supprimer des fichiers ou répertoires
- **Commande :** `hdfs dfs -rm -r <chemin>`
- **Exemple :** Pour supprimer le répertoire `haythem_copie` et son contenu :
  ```bash
  hdfs dfs -rm -r /haythem_copie
  ```

### Nouvelles commandes pour les débutants
#### 10. Changer le nom d'un fichier ou répertoire
- **Commande :** `hdfs dfs -mv <src> <dest>`
- **Exemple :** Pour renommer `haythem_copie` en `nouveau_haythem` :
  ```bash
  hdfs dfs -mv /haythem_copie /nouveau_haythem
  ```

#### 11. Vérifier la taille d'un fichier ou répertoire
- **Commande :** `hdfs dfs -du <chemin>`
- **Exemple :** Pour vérifier la taille du répertoire `haythem` :
  ```bash
  hdfs dfs -du /haythem
  ```

#### 12. Vérifier l'état des fichiers et répertoires
- **Commande :** `hdfs fsck <chemin> -files`
- **Exemple :** Pour vérifier l'état du répertoire `haythem` et ses fichiers :
  ```bash
  hdfs fsck /haythem -files
  ```

Ce tutoriel offre un bon point de départ pour les débutants en HDFS, en combinant les commandes de base et quelques opérations plus avancées pour une meilleure compréhension de l'environnement Hadoop.
