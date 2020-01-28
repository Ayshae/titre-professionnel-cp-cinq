# Dictionnaire de données

## Client (`customer`)

|Champ|Type|Spécificités|Description|
|-|-|-|-|
| id |INT|PRIMARY KEY, NOT NULL, UNSIGNED, AUTO_INCREMENT|L'identifiant du client|
| email | VARCHAR(180) | NOT NULL, UNIQUE |Email du client|
| lastName | VARCHAR(20) | NULL |Nom du client|
| firstName | VARCHAR(20) | NULL |Prenom du client|
| adress | VARCHAR(80) | NULL |Adresse du client|
| postal code | INT(5) | NULL, UNSIGNED |Code postal du client|
| city | VARCHAR(50) | NULL |Ville du client|
| phoneNumber | VARCHAR(14) | NULL |Telephone du client|
| createdAt |TIMESTAMP|NOT NULL, DEFAULT CURRENT_TIMESTAMP|La date de création du client|
| updatedAt |TIMESTAMP|NULL|La date de la dernière mise à jour du client|

## Article (`article`)

|Champ|Type|Spécificités|Description|
|-|-|-|-|
| id |INT|PRIMARY KEY, NOT NULL, UNSIGNED, AUTO_INCREMENT|L'identifiant de l'article|
| designation | VARCHAR(50) | NOT NULL |Designation de l'article|
| price | INT(7) | NOT NULL UNSIGNED|Prix de l'article|
| description | TEXT | NULL |Description de l'article|
| createdAt |TIMESTAMP|NOT NULL, DEFAULT CURRENT_TIMESTAMP|La date de création de l'article|
| updatedAt |TIMESTAMP|NULL|La date de la dernière mise à jour de l'article|

## Commande (`order`)

|Champ|Type|Spécificités|Description|
|-|-|-|-|
| id |INT|PRIMARY KEY, NOT NULL, UNSIGNED, AUTO_INCREMENT|L'identifiant de la commande|
| number | INT(15) | NOT NULL UNSIGNED|Numero de la commande|
| amount | INT(7) | NULL |Montant de la commande|
| customer_id |INT|FOREIGN KEY, NOT NULL, UNSIGNED|L'identifiant relatif au client|
| createdAt |TIMESTAMP|NOT NULL, DEFAULT CURRENT_TIMESTAMP|La date de création de la commande|
| updatedAt |TIMESTAMP|NULL|La date de la dernière mise à jour de la commande|

## Article - Commande (`article_order`)

|Champ|Type|Spécificités|Description|
|-|-|-|-|
| order_id |INT|FOREIGN KEY, NOT NULL, UNSIGNED|L'identifiant relatif à la commande|
| article_id |INT| FOREIGN KEY, NOT NULL, UNSIGNED |L'identifiant relatif à l'article|