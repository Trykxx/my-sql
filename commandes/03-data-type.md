# LMD : Langage de Manipulation de Données (DML: Data Manipulation Language)

```sql
INSERT INTO movie (nom,date_sortie) VALUES ('Pulp Fiction', '2001-10-23'),
('The Revenant', '2015-04-30');
```

```sql
SELECT * FROM movie;
```

```sql
INSERT INTO director (prenom,nom,age,email,date_naissance,salary,pays_d_origine) VALUES ('Spike','Lee','47','spike.lee@gmail.com','1970-05-24','70000,75','US'),('Nolan','Christopher','49','nolan.christopher@gmail.com','1989-06-21','80047,75','US'),('Stan','Lee','47','stan.lee@gmail.com','1969-01-03','40600,95','EN'),('Steven','Spielberg','47','steven.spielberg@gmail.com','1948-10-28','67800,74','FR');
```

INSERT INTO director (prenom,nom,age,email,date_naissance,salary,pays_d_origine) VALUES ('Quentin', 'Tarantino', 58, 'quentin.tarantino@gmail.com', '1963-03-27', 120000.50, 'US'),
('Martin', 'Scorsese', 77, 'martin.scorsese@gmail.com', '1942-11-17', 150000.00, 'US');

```sql
SELECT * FROM director where (conditions)
```

```sql
SELECT * from director WHERE age BETWEEN 40 AND 60;
```

```sql
SELECT * from director WHERE nom LIKE "Lee";
```

```sql
SELECT * from director WHERE prenom IN ("Lee","Stan");
```

<!-- Afficher le prenom et l'email des realisateur dont le nom contient un "e" et ou le pays est FR ou AN et age est supérieur a 30 ans  -->

```sql
SELECT email,prenom FROM director WHERE nom LIKE '%e%' AND pays_d_origine IN ('FR','US') AND age > 30 ORDER BY email;
```

SELECT email,prenom FROM director ORDER BY email;

<!-- Tous les pays seront sur fr pour les id de 1 a 10 -->

```sql
UPDATE director SET pays_d_origine = "FR" WHERE id BETWEEN 0 AND 10;
```

<!-- Mettre le salaire a 1M pour les realisateurs qui ont moins de 20ans ou entre 40 et 60 ans  -->

```sql
UPDATE director SET salary = 1000000 WHERE age < 20 OR age BETWEEN 40 AND 60;
```

<!-- Mettre a jour la colonne salaire pour pouvoir avoir 14 chiffres dont 2 apres la virgule  -->

```sql
ALTER TABLE director MODIFY salary DECIMAL(12,2);
;
```

DELETE FROM director where pays_d_origine NOT IN ('FR','UK');

<!-- Exercice avec une base de données pour des figurine Avengers : -->
<!-- Créez une base de données avec le nom avengers_db : -->
```sql
CREATE DATABASE avengers_db;
```

<!-- Sélectionnez la base de données nouvellement créée : -->
```sql

```



Créez la table "figurine" avec des colonnes telles que "id" (clé primaire), "nom", "super_pouvoir", "annee_sortie" et "description" :
Insérez des données dans la table "figurine" pour représenter des figurine Avengers :
('Iron Man', 'Armure surpuissante', 2008, 'Milliardaire et génie inventeur.'),
('Captain America', 'Force et endurance surhumaines', 2011, 'Héros emblématique de la Seconde Guerre mondiale.'),
('Thor', 'Contrôle de la foudre et marteau magique', 2011, 'Dieu nordique du tonnerre et prince d'Asgard.'),
('Hulk', 'Force et résistance surhumaines', 2008, 'Scientifique transformé en monstre vert lorsqu'il est en colère.'),
('Black Widow', 'Expert en arts martiaux et espionnage', 2010, 'Agent secret russe doté de grandes compétences.'),
('Black Panther', 'Force, vitesse et agilité surhumaines', 2018, 'Roi du Wakanda et protecteur de son peuple.');
Effectuez des requêtes pour afficher les figurine Avengers :
Afficher toutes les figurine :
Afficher les figurine sorties après 2010 :
Afficher les figurine avec le pouvoir "Force" dans leur super_pouvoir :
Modifiez une figurine dans la table "figurine" :
Modifiez la description de "Black Panther" pour "Prince de Wakanda et protecteur de son peuple."
Supprimez la figurine Black Widow de la table "figurine" : 
