<!-- Creer une base de donnees agregation_bd -->
```sql
CREATE DATABASE agregation_bd;
```

<!-- table ville_notation id,nom,note,code_pays -->
```sql
 CREATE table ville_notation(
    id INT PRIMARY KEY AUTO_INCREMENT,
    nom VARCHAR(255),
    note INT,
    code_pays CHAR(2)
 );
```
<!-- Inserer 10 lignes: code_pays: 'fr' 'uk' 'dz'-->
```sql
INSERT INTO ville_notation (nom,note,code_pays) VALUES ('Paris', 5, 'fr'), ('Marseille', 4, 'fr'), ('Lyon', 3, 'fr'), ('Lille', 2, 'fr'), ('Nice', 1, 'fr'), ('Londres', 5, 'uk'), ('Liverpool', 4, 'uk'), ('Manchester', 3, 'uk'), ('Birmingham', 2, 'uk'), ('Glasgow', 1, 'uk'), ('Alger', 5, 'dz'), ('Oran', 4, 'dz'), ('Constantine', 3, 'dz'), ('Annaba', 2, 'dz'), ('Tlemcen', 1, 'dz');
```

<!-- Recuperer le nombre de lignes -->
```sql
SELECT count(*) FROM ville_notation WHERE note > 3;
```

<!-- Recuperer le nombre de lignes ou la note > 3-->
```sql
SELECT count(*) FROM ville_notation WHERE note > 3;
```

<!-- Recuperer la note maximale-->
```sql
SELECT max(note) from ville_notation;
```

<!-- Recuperer la note minimale-->
```sql
SELECT min(note) from ville_notation;
```

<!-- Recuperer la moyenne de notes-->
```sql
SELECT avg(note) from ville_notation;
```

<!-- Selectionner la moyenne des codes_pays -->
```sql
SELECT avg(note),code_pays from ville_notation GROUP BY code_pays;
```
<!-- ajouter une condition sur l'agregation -->
```sql
SELECT avg(note),code_pays from ville_notation GROUP BY code_pays having avg(note) >2;
```
<!-- ORDRE DES CLAUSES -->
```sql
SELECT
FROM
JOIN
WHERE
GROUP BY
HAVING
ORDER BY
LIMIT
```

<!-- Faire la moyenne des notes sans compter les 1 par pays en excluant les moyennes inférieures a 2 -->
```sql
SELECT avg(note),code_pays FROM ville_notation WHERE note != 1 GROUP BY code_pays having avg(note)>2  ORDER BY code_pays;
```