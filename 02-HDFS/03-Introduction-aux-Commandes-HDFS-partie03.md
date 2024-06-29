# Commandes HDFS

### Affichage des fichiers
1. **Lister les fichiers dans HDFS** : `hadoop fs -ls /hdfs/path`
2. **Afficher le contenu d'un fichier** : `hadoop fs -cat /hdfs/path/filename`
3. **Afficher les premières lignes d'un fichier** : `hadoop fs -head /hdfs/path/filename`
4. **Afficher les dernières lignes d'un fichier** : `hadoop fs -tail /hdfs/path/filename`
5. **Afficher les statistiques d'un répertoire** : `hadoop fs -stat /hdfs/path`
6. **Voir les métadonnées des fichiers** : `hadoop fs -stat '%n %b %o %r %y %g %u' /hdfs/path/filename`

### Gestion des fichiers
7. **Copier un fichier local vers HDFS** : `hadoop fs -copyFromLocal /local/path /hdfs/path`
8. **Copier un fichier dans HDFS vers le système de fichiers local** : `hadoop fs -copyToLocal /hdfs/path /local/path`
9. **Envoyer un fichier vers HDFS** : `hadoop fs -put /local/path /hdfs/path`
10. **Récupérer un fichier depuis HDFS** : `hadoop fs -get /hdfs/path /local/path`
11. **Supprimer un fichier** : `hadoop fs -rm /hdfs/path/filename`
12. **Supprimer un répertoire et son contenu** : `hadoop fs -rm -r /hdfs/path/directory`
13. **Déplacer ou renommer un fichier** : `hadoop fs -mv /hdfs/path/source /hdfs/path/destination`

### Création et gestion des répertoires
14. **Créer un répertoire** : `hadoop fs -mkdir /hdfs/path/directory`
15. **Supprimer un répertoire vide** : `hadoop fs -rmdir /hdfs/path/directory`
16. **Lister les répertoires** : `hadoop fs -ls /hdfs/path`
17. **Voir l'espace utilisé par un répertoire** : `hadoop fs -du -h /hdfs/path`
18. **Compter les fichiers et répertoires** : `hadoop fs -count /hdfs/path`

### Modification des permissions et propriétés
19. **Changer les permissions d'un fichier ou répertoire** : `hadoop fs -chmod 755 /hdfs/path/filename`
20. **Changer le propriétaire d'un fichier ou répertoire** : `hadoop fs -chown user:group /hdfs/path/filename`
21. **Changer le groupe d'un fichier ou répertoire** : `hadoop fs -chgrp group /hdfs/path/filename`

### Vérification et maintenance des fichiers
22. **Vérifier un fichier HDFS** : `hdfs fsck /hdfs/path/filename`
23. **Vérifier un répertoire HDFS** : `hdfs fsck /hdfs/path/directory`
24. **Vérifier les blocs d'un fichier** : `hdfs fsck /hdfs/path/filename -files -blocks -locations`
25. **Vérifier l'intégrité d'un fichier** : `hadoop fs -checksum /hdfs/path/filename`

### Autres commandes utiles
26. **Afficher les blocs d'un fichier** : `hdfs fsck /hdfs/path/filename -files -blocks`
27. **Lister les snapshots** : `hadoop fs -ls /hdfs/path/.snapshot`
28. **Créer un snapshot** : `hadoop fs -createSnapshot /hdfs/path snapshot_name`
29. **Supprimer un snapshot** : `hadoop fs -deleteSnapshot /hdfs/path snapshot_name`
30. **Renommer un snapshot** : `hadoop fs -renameSnapshot /hdfs/path snapshot_old_name snapshot_new_name`
31. **Vérifier l'espace restant dans HDFS** : `hadoop fs -df -h /hdfs/path`
32. **Compresser un fichier** : `hadoop fs -compress /hdfs/path/filename`
33. **Décompresser un fichier** : `hadoop fs -uncompress /hdfs/path/filename`
34. **Compter les lignes d'un fichier** : `hadoop fs -count -q /hdfs/path/filename`
35. **Lister les quotas d'un répertoire** : `hadoop fs -count -q /hdfs/path`
36. **Définir un quota pour un répertoire** : `hadoop fs -setQuota /hdfs/path quota`
37. **Supprimer un quota d'un répertoire** : `hadoop fs -clrQuota /hdfs/path`
38. **Voir les utilisateurs ayant accès à un fichier** : `hadoop fs -listAccess /hdfs/path/filename`
39. **Afficher l'historique des commandes HDFS** : `hadoop fs -history`
40. **Exécuter des commandes en tant qu'un autre utilisateur** : `hadoop fs -runAs user command`

### Avancé
41. **Changer la répartition des blocs d'un fichier** : `hadoop fs -setrep -w replication_factor /hdfs/path/filename`
42. **Déplacer un fichier dans un autre espace de noms** : `hadoop fs -moveFromLocal /local/path /hdfs/path`
43. **Synchroniser un répertoire local avec un répertoire HDFS** : `hadoop distcp /local/path /hdfs/path`
44. **Visualiser les logs d'une opération** : `hadoop fs -logLevel`
45. **Lister les fichiers d'un répertoire de manière récursive** : `hadoop fs -ls -R /hdfs/path`
46. **Calculer la taille totale des fichiers** : `hadoop fs -du -s /hdfs/path`
47. **Afficher les erreurs de la commande précédente** : `hadoop fs -showErrors`
48. **Afficher les fichiers avec un filtre spécifique** : `hadoop fs -ls /hdfs/path | grep pattern`
49. **Ajouter une description à un fichier** : `hadoop fs -setfattr -n user.description -v "description text" /hdfs/path/filename`
50. **Afficher les attributs étendus d'un fichier** : `hadoop fs -getfattr -d /hdfs/path/filename`

---

Ces commandes couvrent une large gamme d'opérations que vous pouvez effectuer avec HDFS pour gérer vos fichiers et répertoires dans Hadoop. N'hésitez pas à expérimenter avec ces commandes pour mieux comprendre leur fonctionnement et leurs utilisations pratiques.
