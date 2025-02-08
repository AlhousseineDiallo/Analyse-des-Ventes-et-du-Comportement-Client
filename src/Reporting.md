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

3- **Orders**: 

-   Region: La région de laquelle le client a effectué sa commande.

-   State: Il s'agit là de l'état duquel la commande a été faite.

-   City: Il s'agit de la ville d'où le client a effectué sa commande.

3- **Orders**: 

