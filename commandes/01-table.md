# LDD : Langage de Définition de Données (DDL: Data Definition Language)

### Affichage des tables :
```sql
SHOW TABLES;
```

### Création d'une table :
```sql
CREATE TABLE film(
    id INT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    date_sortie DATE DEFAULT '2000-01-01'
);
```

### Afficher la structure de la table :
```sql
DESCRIBE nom_table;
```

### Afficher le create table :
```sql
SHOW CREATE TABLE nom_table;
```

<!-- creer une table realisateur -->
<!-- id -->
<!-- nom pas le droit d'etre nul-->
<!-- prenom pas le droit d'etre nul -->
<!-- age verifier qu'il a plus de 18 ans -->
<!-- email doit etre unique -->
<!-- date de naissance par default date du jour -->
<!-- salaire pourra etre un nombre a virgule -->

```sql
CREATE TABLE realisateur(
    id INT PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255) NOT NULL,
    prenom VARCHAR(255) NOT NULL,
    age INT UNSIGNED NOT NULL CHECK(age >= 18),
    email VARCHAR(255) UNIQUE,
    date_naissance DATE DEFAULT CURDATE(),
    salaire DECIMAL
);
```

```sql
<!-- On s'est trompé -->
<!-- Renommer la table realisateur en director-->
RENAME TABLE realisateur TO director;

<!-- Renommer la table film en movie -->
RENAME TABLE film TO movie;

<!-- Modifier la table director pour ajouter la colonne pays d'origine => "FR" -->
ALTER TABLE director ADD pays_d_origine CHAR(2);

<!-- Modifier la colonne salaire pour que le type soit décimal (10,2) -->
ALTER TABLE director MODIFY salaire DECIMAL(10,2);

<!-- Modifier le nom d'une colonne -->
ALTER TABLE director CHANGE salaire salary DECIMAL(10,2);

<!-- Modifier la table movie pour rajouter la contrainte unique sur le nom du film  -->
ALTER TABLE movie ADD CONSTRAINT UNIQUE (nom);

<!-- Modifier la colonne nom pour retirer la contrainte unique sur le nom du film  -->
ALTER TABLE movie DROP INDEX nom;

<!-- Creer une table test avec un id -->
CREATE TABLE test(
    id INT UNSIGNED PRIMARY KEY AUTO_INCREMENT
);

<!-- Supprimer la table test -->
DROP TABLE test;

<!-- Ajouter une colonne id_director dans la table movie avec le bon type -->
ALTER TABLE movie ADD COLUMN id_director INT;

<!-- Ajouter une clé secondaire dans la table movie -->
ALTER TABLE movie ADD CONSTRAINT fk_id_director FOREIGN KEY (id_director) REFERENCES director (id);

```

