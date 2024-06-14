<!-- Exercice avec une base de données pour des figurine Avengers : -->
<!-- Créez une base de données avec le nom avengers_db : -->

```sql
CREATE DATABASE avengers_db;
```

<!-- Sélectionnez la base de données nouvellement créée : -->

```sql
USE avengers_db;
```

<!-- Créez la table "figurine" avec des colonnes telles que "id" (clé primaire), "nom", "super_pouvoir", "annee_sortie" et "description" : -->

```sql
CREATE TABLE figurine(
    id INT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    super_pouvoir VARCHAR(255),
    annee_sortie YEAR,
    description VARCHAR(255)
);
```

<!-- Insérez des données dans la table "figurine" pour représenter des figurine Avengers :
('Iron Man', 'Armure surpuissante', 2008, 'Milliardaire et génie inventeur.'),
('Captain America', 'Force et endurance surhumaines', 2011, 'Héros emblématique de la Seconde Guerre mondiale.'),
('Thor', 'Contrôle de la foudre et marteau magique', 2011, 'Dieu nordique du tonnerre et prince d'Asgard.'),
('Hulk', 'Force et résistance surhumaines', 2008, 'Scientifique transformé en monstre vert lorsqu'il est en colère.'),
('Black Widow', 'Expert en arts martiaux et espionnage', 2010, 'Agent secret russe doté de grandes compétences.'),
('Black Panther', 'Force, vitesse et agilité surhumaines', 2018, 'Roi du Wakanda et protecteur de son peuple.'); -->

```sql
INSERT INTO figurine (nom, super_pouvoir, annee_sortie, description)
VALUES
('Iron Man', 'Armure surpuissante', 2008, 'Milliardaire et génie inventeur.'),
('Captain America', 'Force et endurance surhumaines', 2011, 'Héros emblématique de la Seconde Guerre mondiale.'),
('Thor', 'Contrôle de la foudre et marteau magique', 2011, 'Dieu nordique du tonnerre et prince d\'Asgard.'),
('Hulk', 'Force et résistance surhumaines', 2008, 'Scientifique transformé en monstre vert lorsqu\'il est en colère.'),
('Black Widow', 'Expert en arts martiaux et espionnage', 2010, 'Agent secret russe doté de grandes compétences.'),
('Black Panther', 'Force, vitesse et agilité surhumaines', 2018, 'Roi du Wakanda et protecteur de son peuple.');
```


<!-- Effectuez des requêtes pour afficher les figurine Avengers :
Afficher toutes les figurine : -->

```sql
SELECT * FROM figurine;
```

<!-- Afficher les figurine sorties après 2010 : -->
```sql
SELECT * FROM figurine WHERE annee_sortie > 2010;
```

<!-- Afficher les figurine avec le pouvoir "Force" dans leur super_pouvoir : -->
```sql
SELECT * FROM figurine WHERE super_pouvoir LIKE '%Force%';
```

<!-- Modifiez une figurine dans la table "figurine" :
Modifiez la description de "Black Panther" pour "Prince de Wakanda et protecteur de son peuple." -->
```sql
UPDATE figurine SET description = 'Prince de Wakanda et protecteur de son peuple.' WHERE nom = 'Black Panther';
```

<!-- Supprimez la figurine Black Widow de la table "figurine" : -->
```sql
DELETE FROM figurine WHERE nom = 'Black Widow';
```

<!-- Créer la table "weapon" avec des colonnes telles que "id" (clé primaire), "nom", "description" : -->
```sql
CREATE TABLE weapon(
    id INT UNSIGNED PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    description TEXT
);
```

<!-- Insérez des données dans la table "weapon" pour représenter des armes Avengers : -->
```sql
INSERT INTO weapon (nom, description)
VALUES('Marteau', 'Marteau magique de Thor.'),
    ('Bouclier', 'Bouclier indestructible.'),
    ('Arc et flèches', 'Arc et flèches de Hawkeye.'),
    ('Armure', 'Armure spéciale conçue pour combattre Hulk.'),
    ('Vibranium Claws', 'Griffes en vibranium indestructible .');
```

<!-- Modifier la table "figurine" pour ajouter une colonne "weapon_id" : -->

```sql
ALTER TABLE figurine ADD weapon_id INT UNSIGNED;
```

<!-- Modifier la table "figurine" pour ajouter une contrainte de clé étrangère avec la table "weapon" : -->
```sql
ALTER TABLE figurine ADD CONSTRAINT fk_id_weapon FOREIGN KEY (weapon_id) REFERENCES weapon(id);
```

<!-- Mettre la table "weapon" en relation avec la table "figurine" : -->
```sql
UPDATE figurine SET weapon_id = 4 WHERE nom = 'Iron Man';
```

```sql
SELECT * FROM figurine INNER JOIN weapon ON weapon_id = weapon.id;
```

<!-- non avenger et arme dont annee de sortie > 2010> -->
```sql
SELECT figurine.nom,weapon.nom FROM figurine INNER JOIN weapon ON weapon_id = weapon.id WHERE figurine.annee_sortie>2010;
```

<!-- recuperer le nom des figurines qui n'ont pas d'armes -->
```sql
SELECT figurine.nom FROM figurine LEFT JOIN weapon ON figurine.weapon_id = weapon.id WHERE weapon.id IS NULL;
```
