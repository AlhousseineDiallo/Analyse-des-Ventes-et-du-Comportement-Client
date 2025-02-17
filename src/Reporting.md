# Rapport d' Analyse

## Introduction

Ce projet présente une analyse approfondie des données de vente et de comportement des clients d'une entreprise de la grande distribution pour la période 2020 à 2023. L'objectif de ce projet est de fournir une compréhension claire des performances, d'identifier les tendances et les opportunités d'amélioration et soutenir, de permettre la prise de décisions stratégiques grâce à des insights basées sur les données. Ce projet a vu le jour suite à la demande de la direction d'obtenir une vue d'ensemble des dindicateurs clés de performances(KPI), des tendances ds ventes et des clients, de la performance de chaque sous catégorie de produit et par extension de chaque catégorie afin d'optimiser les stratégies de vente et de marketing.

## Objectif du projet d'analyse:
Les objectifs de ce projet sont pléthoriques, ces derniers visent notamment à fournir une compréhension globale de la performance commerciale de notre entreprise et de détecter des tendances dans le comportement des clients. Ainsi les objectifs sont les suivants:

1- **Créer des tableaux de bords interactifs:** pour faciliter l'exploration des données, le suivi des KPI et la communication des résultats aux parties prenantes de l'entreprise.

2- **Analyser les performances des ventes d'une année à l'autre:** Cela concerne les ventes, les quantités, les profits entres autres, ainsi nous pourrons identifier les taux de croissances, les tendances saisonnières et les variations significatives.

3- **Comprendre les tendances et les profits: ** Le but ici est de détecter les tendances mensuelles et hebdomadaires pour identifier les périodes de forte et de faible performance, aussi les cycles de ventes et anticiper les besoins futurs.

4- **Identifier les segments de clientèles les plus rentables:** Ce but vise à concentrer les efforts marketing et de fidélisation.

5- **Fournir des recommandations basées sur les données** pour améliorer les stratégies de vente, de marketing, de gestion des stocks et de relations clients.

6- **Établir une baser pour des analyses futures** reproductibles et évolutives.

## Méthodologie

Le projet a été mené en suivant les étapes clés du cycle de vie d'une analyse de données, en adoptant une approche rigoureuse et précise pour garantir la fiabilité et la pertinence des résultats.

### 3.1 Collecte des données
Les données utilisées proviennent d’une base de données interne au format SQL, consolidant les informations des clients, des produits et des transactions. Elles ont été extraites via une requête SQL optimisée et enregistrées sous format .csv pour l’importation dans Tableau. Ces données se résument en quatre fichiers csv répresentant différents secteurs d'activités de l'entreprise:

**Customers.csv**: Cette table fournit des informations détaillées sur les clients, telles que l'indentifiant client, le nom, le segment, et d'autres attributs démographiques pertinents.

**Location.csv**: Elle regroupe les informations géographiques relatives aux ventes, telles que la région, le pays et la ville.

**Orders.csv**: Contient les transactions détaillées, incluant les informations sur les ventes, les quantités, les prix et les dates des commandes.

**Products.csv**: Cette table comprend les caractéristiques des produits, comme l'indentifiant produit, le nom, la catégorie, la sous catégorie.

### 3.2 Description des données et des Jointures effectuées

Les données utilisées proviennent de quatre fichiers CSV, chacun contenant des informations spécifiques sur les clients, les produits, la localisation des commandes et enfin les commandes. Pour obtenir une vue d'ensemble et analyser les relations entre ces différents éléments, il a été nécessaire de combiner ces fichiers en utilisant une technique nommée: jointure.

#### Tables et colonnes utilisées:
Avant d'expliquer comment nous avons assemblé les différentes pièces, voici un petit aperçu de chaque table:

1- **Customers**: Cette table contient toutes les informations sur nos clients. Elle regroupe entre autres.
-   Customer ID: C'est le champ qui permet d'identifier chaque clients de façon unique.

-   Customer Name: C'est le nom complet du client.


2- **Location**: Cette table contient toutes les informations géographiques relatives aux commandes:
-   Postal Code: C'est le code postal qui sert de clé primaire à cette table.ù le client a effectué sa commande.


-   Region: La région de laquelle le client a effectué sa commande.

-   State: Il s'agit là de l'état duquel la commande a été faite.

-   City: Il s'agit de la ville d'où le client a effectué sa commande.

- Country/Region: Cette colonne spécifie l'état ou le pays depuis lequel la commande a été effectué.



3- **Orders**: Il s'agit de la table qui se trouve au coeur de notre analyse, elle contient les principales métriques de notre ensemble de données:

- Order ID: Un numéro unique qui identifie chaque commande, il constitue la clé primaire de notre table.

- Order Date, Ship Date: Il s'agit des dates de commandes et d'expédition.

- Sales, Profit, Quantity: Il s'agit respectivement du montant des ventes, du profit réalisé et de la quantité de produits par commande.

- Customer ID: Il constitue un numéro unique associé à chaque client pour l'identifier de façon unique. Il est également présent en tant que clé primaire dans la table Customers et jouera par conséquent le rôle de clé étrangère pour relier cette table à la table Customers

- Postal Code: Il s'agit du code postal du lieu d'où la commande a été faite, il sert de clé étrangère qui nous permet de relier les commandes aux localisations dans la table Location.

- Product ID: Il s'agit de l'identifiant du produit commandé, il est une clé étrangère qui relie la table Orders à la table Products.


#### Jointures réalisées:
Les données étant de haute qualité, aucun nettoyage n’a été nécessaire. Elles ont été importées telles quelles dans Tableau après vérification de leur intégrité.

Aussi le  modèle relationnel repose sur le système (fact table + dimensions), ici en l'occurence notre fact table est la table Orders qui contient nos métriques clés et les dimensions sont les tables Products, Customers et Location qui vont toutes étres reliées à notre fact table par le biais des clés étrangères qu'elle contient(Customer ID, Product ID, Postal Code).

Maintenant  voici une description de comment la jointure a été faite, en précisant la raison, le but qui a motivé les jointures entre nos différentes tables:
1. **Relier les commandes aux clients (Orders ↔ Customers)** :
    *   **Pourquoi ?** Pour savoir quel client a passé quelle commande.
    *   **Comment ?** En utilisant le champ `Customer ID` qui est présent dans les deux tables (**Orders** et **Customers**). On fait correspondre le `Customer ID` de la table **Orders** avec le `Customer ID` de la table **Customers**.
    *   **Résultat** : On peut maintenant dire, par exemple, "Le client Jean Dupont (dont l'ID est CUST-001) a passé la commande ORD-123".

2. **Relier les commandes aux localisations (Orders ↔ Location)** :
    *   **Pourquoi ?** Pour savoir où les commandes ont été passées et expédiées.
    *   **Comment ?** En utilisant le champ `Postal Code`. On fait correspondre le `Postal Code` de la table **Orders** avec le `Postal Code` de la table **Location**.
    *   **Résultat** : On peut maintenant dire, par exemple, "La commande ORD-123 a été passée dans la région Nord, dans l'état de Californie, ville de Los Angeles".

3. **Relier les commandes aux produits (Orders ↔ Products)** :
    *   **Pourquoi ?** Pour savoir quels produits ont été vendus dans chaque commande.
    *   **Comment ?** En utilisant le champ `Product ID`. On fait correspondre le `Product ID` de la table **Orders** avec le `Product ID` de la table **Products**.
    *   **Résultat** : On peut maintenant dire, par exemple, "La commande ORD-123 contient le produit PROD-456, qui est une chaise de la catégorie Meubles".

**En résumé** : Grâce aux jointures, nous avons créé une grande table qui combine toutes les informations de nos quatre fichiers d'origine. Cette table enrichie nous permettra de faire des analyses beaucoup plus poussées et de répondre à des questions comme :

*   Quels sont les produits les plus vendus par tel client ?
*   Quelle est la région qui génère le plus de profit ?
*   Quelles sont les catégories de produits les plus populaires dans telle ville ?

Cette table consolidée est la base de notre analyse et des visualisations que nous allons présenter dans les tableaux de bord. Elle nous permet d'avoir une vision globale et détaillée des performances de l'entreprise et du comportement des clients.


Cette capture d'écran du modèle relationnelle permettra une meilleure compréhension de ce dernier.
![Modèle Relationnel](https://github.com/AlhousseineDiallo/Sales_Dashboard/blob/087dcc6dd71afe8bb8dcf471b3f292eeb8d57cc1/modele.relationnel.png)


### 3.3 Choix des Variables et Interactions

Les variables ont été choisies pour leur pertinence par rapport aux objectifs stratégiques.

#### Principales Variables et Interactions :

1. **Analyse des ventes** : `Sales`, `Profit`, `Quantity` (de notre fact table **Orders**), qui ont été associés avec les catégories et sous-catégories de produits (de la table **Products**).

2. **Analyse temporelle** : `Order Date`, `Ship Date` pour évaluer les tendances saisonnières et détecter les pics de performance.

3. **Analyse client** : `Order ID`, `Customer_ID` qui ont permis de déterminer la distribution de nos données et (`Sales`, `Profit`) pour identifier et  prioriser les clients les plus rentables.

### 3.4 Variables Calculées

*   **Croissance des ventes d'une année sur l'autre (%)** : `(Ventes année en cours - Ventes année précédente) / Ventes année précédente * 100`

*   **Croissance des bénéfices d'une année sur l'autre (%)** : `((Profit année en cours - Profit année précédente) / Profit année précédente * 100`

*   **Moyenne des ventes hebdomadaires** : `Somme des ventes de chaque semaine / Nombre de semaines`

*   **Moyenne des bénéfices hebdomadaires** : `Somme des bénéfices de chaque semaine / Nombre de semaines`

*   **Vente de l'année en cours par client (%)**:  `Vente année en cours / Nombre de clients`

### 3.5 Conception et Implémentation du Tableau de Bord

Deux tableaux de bord interactifs ont été crées, un pour les ventes et un pour les clients, en utilisant l'outil de visualisation de données Tableau Desktop Public. La conception des tableaux de bord a été guidée par les principes suivants: clarté, simplicité et enfin interactivité, afin de faciliter l'exploration des données et la communication des résultats. Dans les lignes qui suivent j'expliciterai le contenu de ces différents tableaux de bords.

#### 3.5.1 Tableau de Bord des Ventes

Ce tableau de bord offre une vue d'ensemble complète des performances des ventes, permettant aux utilisateurs d'analyser les KPI, les tendances et la performance des catégories ou sous-catégories de produits de manière interactive.

##### 3.5.1. 1 KPI (Indicateurs Clés de Performance)
*   Le tableau de bord affiche en évidence les KPI suivants pour l'année en cours avec la possibilité de changer l'année de manière interactive :
    *   **Ventes totales** : Chiffre d'affaires total généré.

    *   **Profit total** : Bénéfice total réalisé.

    *   **Quantité vendue** : Nombre total d'unités vendues.
*   Pour chaque KPI, le pourcentage de variation par rapport à l'année précédente est également affiché, permettant une évaluation rapide de la croissance et/ou de la décroissance.

*   **[Screenshot KPI]()**
*   **Description** : Cette section du tableau de bord présente les indicateurs clés de performance (KPI) pour l'année sélectionnée au niveau de la section filtre et l'année précédente. Chaque KPI (Ventes totales, Profit total, Quantité vendue) est affiché avec sa valeur actuelle et le pourcentage de variation par rapport à l'année précédente.

##### 3.5.1. 2 Tendances des ventes :
*   Des graphiques linéaires interactifs montrent les tendances mensuelles des ventes, des bénéfices et des quantités pour l'année sélectionnée dans la section des filtres et l'année précédente.
*   Les points peuvent être survolé pour obtenir les valeurs exactes pour chaque mois.
*   Des marqueurs de couleur mettent en évidence les mois avec les performances les plus élevées et les plus faibles pour l'année en cours, facilitant l'identification des pics et des creux.
*   **[Screenshot Graphique des tendances mensuelles des KPI]()**
*   **Description** : Ce graphique linéaire présente les tendances mensuelles des trois KPI (Ventes, Profit, Quantité) pour l'année sélectionnée dans la section des filtres  (en noir) et l'année précédente (gris clair). Des marqueurs circulaires de couleur verte indiquent les mois avec la meilleure performance pour l'année en cours, c'est à dire celle sélectionnée dans la section des filtres.

##### 3.5.1. 3 Comparaison des sous-catégories de produits:
*   Des graphiques à barres(ou en tuyaux d'orgue) interactifs permettent de comparer les ventes générés par chaque sous-catégorie de produit pour l'année en cours et l'année précédente, avec la possibilité de distinguer les catégories dont les ventes ont diminué par rapport à l'année précédente par le biais d'un point rouge.

* Notons que les barres en noires représentent celles de l'année en cours et celles en gris claires ceux de l'année précédente.
*   L'utilisateur peut cliquer sur une barre pour filtrer les autres visualisations du tableau de bord et se concentrer sur une sous-catégorie spécifique.
*   Un graphique à barres supplémentaire illustre les profits par sous-catégorie, permettant une comparaison directe avec les performances des ventes.
*   **[Screenshot Graphiques à barres des ventes et profits par sous-catégorie]()**
*   **Description** :  Cette section du tableau de bord présente deux graphiques à barres. Le premier compare les ventes par sous-catégorie pour l'année en cours et l'année précédente. Le second graphique illustre les profits générés par chaque sous-catégorie pour l'année en cours.

##### 3.5.1. 4 Tendances hebdomadaires :
*   Deux graphiques en escalier (ou step chart en anglais) distincts montrent les tendances hebdomadaires des ventes et des bénéfices(profits) pour l'année en cours(c'est à dire l'année qui est actuellement sélectionnée dans la section filtre).

*   Une ligne de tendance en pointillé représente la moyenne hebdomadaire pour chaque KPI, facilitant l'identification des semaines performantes et sous-performantes.
*   Un dégradé de couleur du bleu au rouge est utilisé pour indiquer les semaines qui sont au-dessus ou en dessous de la moyenne, attirant l'attention sur les variations significatives.
*   **[Screenshot Graphiques des tendances hebdomadaires des ventes et profits]()**
*   **Description** : Cette section présente deux graphiques linéaires illustrant les tendances hebdomadaires des ventes et des profits pour l'année en cours. Une ligne de tendance en pointillé indique la moyenne hebdomadaire pour chaque KPI. Les zones au-dessus de la moyenne sont colorées en bleu, tandis que les zones en dessous sont colorées en rouge.

##### 3.5.1. 5 Filtres :
*   Le tableau de bord intègre des filtres interactifs qui permettent à l'utilisateur d'explorer les données de manière dynamique et d'obtenir des vues personnalisées.

*   **Filtre par année** : Permet de sélectionner l'année à afficher (année en cours et par prolongement l'année précédente).
*   **Filtre par catégorie de produit** : Permet de sélectionner une ou plusieurs catégories de produits pour filtrer les données.
*   **Filtre par sous-catégorie de produit** : Permet de sélectionner une ou plusieurs sous-catégories de produits.
*   **Filtre par région** : Permet de sélectionner une ou plusieurs régions géographiques.
*   **Filtre par État** : Permet de sélectionner un ou plusieurs États.
*   **Filtre par ville** : Permet de sélectionner une ou plusieurs villes.
*   **[Screenshot Filtres]**()
*   **Description** : Cette section du tableau de bord montre les différents filtres disponibles pour explorer les données. On peut voir des menus déroulants pour filtrer par année, catégorie de produit, sous-catégorie de produit, région, État et ville.
