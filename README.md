# Dashboard d'Analyse des ventes et des clients - Projet Data Analytics

---

## Structure du Répertoire
Le projet est structuré comme suit:

- **README.md**: Ce fichier fournit une vue d'ensemble du répertoire github et donne les exigences ou besoins nécessaires à la bonne conduite du projet.
- **src/**: Ce dossier contient les datasets(Ensembles de données) qui ont servi pour le projet et les fichiers qui ont résulté de mon analyse.
  - **EU-Dataset/**: contient les différents fichiers qui ont été utilisés pour ce projet.
  - **Tableau Dashboard/**: qui contient les différents tableaux de bords qui ont été générés conformément aux requêtes et exigences expliciter dans les exigences et besoins.
  - **Reporting/**: constitue le rapport qui a émergé de ce projet, il présente notamment une interprètation détaillée des résultats qui ont découlé du tableau de bord, aussi il met en évidence les insights et les recommandations stratégiques et opérationnelles pour permettre à l'entreprise d'atteindre ses objectifs.
 
## Introduction
Bienvenue dans le projet d'Analyse des Ventes et du Comportement Client. Ce projet retrace le parcours d'une analyse approfondie visant à décrypter les performances commerciales et le comportement des Clients d'une entreprise de la grande distribution, acteur majeur de son secteur et basé aux États-Unis. Vous trouverez tout au long de votre cheminement les données utilisées, un rapport détaillé ainsi qu'un tableau de bord interactif, permettant d'appréhender les ventes et les clients sous toutes les coutures.


Dans un environnement commercial de plus en plus concurrentiel, une compréhension fine des performances des ventes et du comportement, des tendances de la clientèle est devenue un enjeu crucial voire capital. Ainsi ce projet a pour vocation de fournir une vision claire et nette des indicateurs clés de performance (KPI), des tendances et évolutions temporelles des ventes et du comportement des clients.

## Fonctionnalités et exigences du Dashboard:
Cette section détaille les exigences et besoins des tableaux de bords, en mettant en évidence les principaux indicateurs clés de performances (KPI) à intégrer pour assurer une analyse efficace et pertinente des données. Ces indicateurs et visualisations de données permettront aux parties prenantes et aux différents managers et cadres de tirer le meilleur de leurs données et ainsi de prendre des décisions éclairées. Afin de répondre efficacement aux exigences définies et d'offrir une analyse claire et ciblée, deux tableaux de bord distincts seront crées, un pour les ventes et l'autre sur les clients. Ainsi dans les lignes qui suivent nous allons mettre l'accent sur le contenu de chaque dashboard:

### Le tableau de bord des ventes:
L'objectif du tableau de bord des ventes est de fournir un aperçu des indicateurs et tendances des ventes afin d'analyser la performance des ventes d'une année sur l'autre et de mieux comprendre les tendances des ventes.
Les exigences clés sont les suivantes:

- Aperçu des KPI:
  - Afficher les ventes totales, des profits et des quantités pour l'année en cours et l'année précédente.

- Tendances des ventes:
  - Présenter les données de chaque KPI sur une base mensuelle pour l'année en cours et l'année précédente.

  - Identifier les mois avec les ventes les plus élevées et les plus faibles, et les rendre facilement reconnaissables.

- Comparaison des sous-catégories de produits:
  - Comparer la performance des ventes selon différentes sous-catégories de produits pour l'année en cours et l'année précédente.

  - Inclure une comparaison entre les ventes et les profits pour chacune des sous-catégories.

- Tendances hebdomadaires des ventes et des profits:
  - Présenter les données hebdomadaires des ventes et des profits pour l'année en cours.

  - Afficher les valeurs moyennes hebdomadaires à l'aide d'une ligne de référence.

  - Mettre en évidence les semaines au-dessus et en dessous de la moyenne afin d'attirer l'attention sur la performance des ventes et des profits.



### Le tableau de bord des Clients:
Le tableau de bord des Clients vise à fournir un aperçu des données clients, des tendances et des comportements. Il aidera les équipes marketing et la direction à mieux comprendre les segments de clientèle et à améliorer la satisfaction des clients. Les exigences clés sont les suivantes:

- Aperçu des KPI(Indicateurs Clés de Performance):
  - Afficher le nombre total de clients, le total des ventes par clients et enfin le total des commandes pour l'année en cours et l'année précédente.

- Tendances des Clients:
  - Présenter les données de chaque KPI sur une base mensuelle pour l'année en cours et l'année précédente.

  - Identifier les mois avec les ventes les plus élevées et les plus faibles, et les rendre facilement reconnaissables.

- Répartition des clients par nombre de commandes:
  - Représenter la répartition des clients en fonction du nombre de commandes passées afin de fournir des informations sur leur comportement, leur fidélité et leur engagement.

- Top 10 des clients par profit:
  - Présenter les 10 clients ayant généré les profits les plus élevés pour l'entreprise.

  - Afficher des informations supplémentaires telles que le classement, le nombre de commandes, les ventes actuelles, le profit actuel et la date de la dernière commande.

### Exigence en matière de conception et d'interactivité:

- Dynamisme du tableau de bord:
  - Le tableau de bord doit permettre aux utilisateurs de consulter les données historiques en leur offrant la flexibilité de sélectionner l'année de leur choix.

  - Offrir aux utilisateurs la possibilité de naviguer facilement entre les différents tableaux de bord.

  - Rendre les graphiques interactifs afin de permettre aux utilisateurs de filtrer les données directement à partir des graphiques.

- Filtres de données:
  - Le tableau de bord devra permettre aux utilisateurs de filtrer les données en fonction des informations sur les produits, telles que la catégorie et la sous-catégorie, ainsi qu'en fonction des informations géographiques, telles que la région, l'État et la ville.


## Méthodologie

### Données utilisées:
Les données utilisées proviennent de quatres fichiers CSV (Customers.csv, Order.csv, Location.csv, Products.csv) qui ont été fournis. Ces données d'une structure fiable  et de haute qualité n'ont donc pas nécessité de nettoyage, car les données étaient déjà prêtes pour l'analyse, respectant les normes de qualité requises pour ce projet.

### Modélisation des données dans Tableau:
Pour assurer une analyse efficace et appronfondie des données, une modélisation relationnelle a été mise en place dans Tableau. Dans cette dernière les tables sont reliées de manière logique en utilisant des clés primaires et étrangères appropriées pour garantir l'intégrité des données et optimiser les analyses. Ainsi la table Orders est connectée aux dimensions Customers, Products et Location, permettant une exploration multidimensionnelle efficace.

- Détail de la modélisation:
  - Table de faits(Orders): Contient les transactions détaillées, incluant les informations sur les ventes, les quantités, les prix et les dates des commandes. Elle constitue la pierre angulaire de notre modèle relationnelle.

  - Table des clients (Customers): Cette table fournit des informations détaillées sur les clients, telles que l'indentifiant client, le nom, le segment, et d'autres attributs démographiques pertinents.

  - Table des produits (Products): Cette table comprend les caractéristiques des produits, comme l'indentifiant produit, le nom, la catégorie, la sous catégorie.

  - Table des localisations (Location): Elle regroupe les informations géographiques relatives aux ventes, telles que la région, le pays et la ville.

  Cette capture d'écran du modèle permettra une meilleure compréhension de ce dernier:
  ![Modèle Relationnel](https://github.com/AlhousseineDiallo/Sales_Dashboard/blob/087dcc6dd71afe8bb8dcf471b3f292eeb8d57cc1/modele.relationnel.png)
  





    
    
