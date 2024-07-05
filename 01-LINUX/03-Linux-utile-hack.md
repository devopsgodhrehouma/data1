### Tuto détaillé pour les étudiants débutants en utilisant le terminal Linux

# Référence :
- https://faun.pub/essential-linux-terminal-hacks-for-efficiency-part-2-84c1036d8258

# Tutoriel détaillé avec des lignes de commande à essayer pour les débutants en utilisant le terminal Linux. 
- Chaque section inclut des explications et des commandes à tester.

#### 1. Recherche inversée des commandes
Pour réutiliser une commande, utilisez `Ctrl + R` et tapez quelques mots-clés correspondants pour voir les commandes récemment utilisées.

```bash
# Essayez de taper Ctrl + R, puis tapez 'ls' pour trouver la dernière commande 'ls'.
```

#### 2. Utiliser une commande particulière de l'historique
Utilisez la commande `history` pour lister toutes les commandes précédentes, et utilisez `!<numéro>` pour réutiliser la commande.

```bash
history
!767  # Remplacez 767 par le numéro de la commande que vous souhaitez réutiliser
```

#### 3. Afficher la date et l'heure dans l'historique
Pour voir la date et l'heure dans l'historique des commandes, utilisez `HISTTIMEFORMAT`.

```bash
HISTTIMEFORMAT="%d-%m-%y %r " history
# Pour le définir de manière permanente, ajoutez dans .bashrc
echo 'export HISTTIMEFORMAT="%d-%m-%y %r "' >> ~/.bashrc
source ~/.bashrc
```

#### 4. Exécuter plusieurs commandes à la fois
Chainez plusieurs commandes ensemble avec trois options.

```bash
# Exécution séquentielle
cmd1; cmd2; cmd3

# Exécution conditionnelle (cmd2 ne s'exécute que si cmd1 réussit)
cmd1 && cmd2

# Exécution conditionnelle (cmd2 ne s'exécute que si cmd1 échoue)
cmd1 || cmd2
```

#### 5. Visualiser le contenu avec `less`
Pour visualiser un fichier volumineux sans saturer l'écran.

```bash
less /path/to/your/file
```

#### 6. Afficher en format tabulaire avec `column`
Utilisez la commande `column` pour afficher le contenu en format tabulaire.

```bash
column -s ',' -t data.csv  # Pour un fichier CSV avec des valeurs séparées par des virgules
cat /etc/passwd | column -s ':' -t  # Pour afficher le fichier passwd de manière lisible
```

#### 7. Tronquer un fichier
Supprimez le contenu d'un fichier sans l'ouvrir avec `truncate`.

```bash
truncate -s 0 filename.txt  # Supprime tout le contenu
truncate -s 100 filename.txt  # Réduit la taille du fichier à 100 octets
```

#### 8. Utiliser `head` et `tail`
Affiche les premières ou dernières lignes d'un fichier.

```bash
head -n 20 filename.txt  # Affiche les 20 premières lignes
tail -n 20 filename.txt  # Affiche les 20 dernières lignes
tail -f filename.txt  # Suivre les ajouts en temps réel
```

#### 9. Voir le code de sortie
Les codes de sortie montrent les résultats de l'exécution, utiles pour les scripts shell.

```bash
echo $?  # Affiche le code de sortie de la commande précédente
```

#### 10. Créer des répertoires imbriqués
Utilisez `mkdir -p` pour créer des répertoires imbriqués.

```bash
mkdir -p dir/{dir1/subdir1,dir2,dir3/subdir3}
```

#### 11. Commande `file`
Utilisez `file` pour vérifier le type de n'importe quel fichier.

```bash
file /path/to/your/file
```

Ces commandes offrent un bon point de départ pour les débutants souhaitant améliorer leur efficacité en utilisant le terminal Linux. N'hésitez pas à les essayer et à explorer davantage les options et les fonctionnalités de chaque commande.
