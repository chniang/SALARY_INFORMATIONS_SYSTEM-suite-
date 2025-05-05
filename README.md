📄 README - Base de données salary_informations_system (suite)
📘 Description
La base de données salary_informations_system est conçue pour gérer des informations liées aux employés, départements, projets et affectations aux projets au sein d'une entreprise.

Elle contient les entités suivantes :

Departement

Employe

Projet

Employe_Projet

🗂 Structure des Tables
1. Departement
Colonne	Type	Description
Num_S	INT (PK)	Identifiant du département
Label	VARCHAR(50)	Nom du département
Manager_Name	VARCHAR(100)	Nom du responsable

2. Employe
Colonne	Type	Description
Num_E	INT (PK)	Identifiant de l'employé
Nom	VARCHAR(100)	Nom de l'employé
Position	VARCHAR(50)	Poste occupé
Salaire	DECIMAL(10,2)	Salaire de l'employé
Departement_Num_S	INT (FK)	Département d'appartenance

3. Projet
Colonne	Type	Description
Num_P	INT (PK)	Identifiant du projet
Titre	VARCHAR(100)	Titre du projet
Date_de_debut	DATE	Date de début du projet
Date_de_fin	DATE	Date de fin du projet
Departement_Num_S	INT (FK)	Département en charge du projet

4. Employe_Projet
Colonne	Type	Description
Employe_Num_E	INT (FK)	Identifiant de l'employé
Projet_Num_P	INT (FK)	Identifiant du projet
Role	VARCHAR(100)	Rôle de l'employé dans le projet

📥 Opérations DML effectuées
✅ Insertion des données
Les données ont été insérées pour chaque table conformément aux spécifications fournies.
Voir le fichier SQL salary_informations_system.sql pour les requêtes INSERT INTO.

✏️ Mise à jour
Le rôle de l’employé Num_E = 101 dans la table Employe_Projet a été mis à jour :

sql:

UPDATE Employe_Projet
SET Role = 'Full Stack Developer'
WHERE Employe_Num_E = 101 AND Projet_Num_P = 201;
❌ Suppression
L'employé Num_E = 103 a été supprimé, ainsi que ses affectations à des projets :

sql:

DELETE FROM Employe_Projet WHERE Employe_Num_E = 103;
DELETE FROM Employe WHERE Num_E = 103;
🚀 Comment exécuter le projet
Ouvrir votre environnement SQL (ex. : phpMyAdmin, MySQL Workbench).

Créer la base de données :
sql:

CREATE DATABASE salary_informations_system;
USE salary_informations_system;
Exécuter le script SQL salary_informations_system.sql pour créer les tables et insérer les données.

Tester les requêtes de mise à jour et de suppression.

