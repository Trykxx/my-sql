# Quelques commandes de base pour interagir avec une base de données MySQL :

### Version de MySQL :
```sql
mysql --version
```

### Connexion a MySQL
```sql
mysql -u nom_utilisateur -p
```

### Deconnexion de MySQL
```sql
quit ou exit
```

### Afficher les bases de données
```sql
SHOW DATABASES;
```

### Création d'une base de données
```sql
CREATE DATABASE nom_bdd;
```

### Supression d'une base de données
```sql
DROP DATABASE nom_bdd;
```

### Sélection de la base de données
```sql
USE nom_bdd;
```

TODO a demander
### Sauvegarde de la base de données
```sql
mysqldump -u nom_utilisateur -p nom_bdd > db.sql
```

# Ce ne sont là que quelques-unes des commandes de base pour MySQL.
# Il existe de nombreuses autres fonctionnalités et commandes avancées disponibles pour interagir avec une base de données MySQL.