# Documentation technique - Sales Dashboard Project

---

## Structure du Répertoire
Le projet est structuré comme suit:

- **README.md**: Ce fichier fournit une vue d'ensemble du repo et donne les exigences ou besoins nécessaires à la bonne conduite du projet.
- **src/**: Ce dossier contient les datasets(Ensembles de données) qui ont servi pour le projet et les fichiers liés à l'analyse.
  - **data/**: contient les différents fichiers qui ont été utilisés pour ce projet.
  - **Tableau Dashboard/**: qui contient les différents tableaux de bords qui ont été générés conformément aux requêtes et exigences expliciter dans les requirements.
  - **Reporting/**: contient les différents rapports redigés lors de la création des tableaux de bords.
 
## 1. Introduction
Ce fichier décrit de façon exhaustive le processus ayant permis de mener a bien ce projet par le biais des exigences notamment, aussi il explicite les étapes de chargement et de modélisation des données dans le logiciel Tableau Desktop.

## 2. Chargement et Modélisation des données:
### 2.1 Chargement des données:
Les données ont été chargées à partir de 4 fichiers csv, à savoir le fichier customers, location, orders et enfin products qui contiennent les données d'un magasin de vente basé aux USA.

### 2.3 Description des différentes tables:
  - Customers: Contient les différentes informations sur les clients tels que leurs noms et leurs identifiants.
  - Products: Contient les détails sur les produits tels que leurs catégories, leurs sous-catégories, leurs noms et enfin leurs identifiants.
  - Location: Contient les informations sur les lieux, comme les régions, les états, les villes et les codes postaux.
  - Orders: Elle est la table principale et contient de ce fait toutes les informations sur les commandes, leurs montants et les dates correspondantes.

### 2.2 Modélisation des données:
Pour analyser efficacement les données, j'ai organisé mes tables de manière logique afin de faciliter les connexions entre elles. Ainsi j'ai commencé par la Fact Table, c'est à dire la table Orders qui contient les informations principales tels que les montants des commandes et leurs dates correspondantes, elle est donc au coeur de mon modèle, ensuite j'ai connecté la table Orders aux autres tables(Dimension Tables) qui permettent d'enrichir l'analyse en segmentant et en regroupant les données.


## 3. Exigences:
Les différentes images suivantes nous donnent les besoins et de ce fait les spécificités qu'auront les futures Tableaux de bords:
  - Sales Dashboard:
![Exigences du Tableau de Bord des Ventes](https://github.com/AlhousseineDiallo/Sales_Dashboard/blob/4d6147a20d5ec7de4f9043acf3d3447f7862ca87/image/Screenshot%202025-01-15%20021144.png)


- Customer Dashboard:
![Exigences du Tableau de Bord des Clients](https://github.com/AlhousseineDiallo/Sales_Dashboard/blob/4d6147a20d5ec7de4f9043acf3d3447f7862ca87/image/Screenshot%202025-01-15%20005959.png)


- Les critères de design et d'interactivités:
![](https://github.com/AlhousseineDiallo/Sales_Dashboard/blob/4d6147a20d5ec7de4f9043acf3d3447f7862ca87/image/Screenshot%202025-01-15%20022523.png)

    
    
