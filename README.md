🎬 Projet MovieLens – Phase 4

Système de recommandation de films

Auteur : Rodolphe CHARLES
Encadrement : M. Wedter JEROME & Geovany Batista LAGUERRE
Octobre 2025
🔗 LinkedIn : www.linkedin.com/in/rodolphecharles


📘 Contexte et justification

L’essor des plateformes de streaming (Netflix, Amazon Prime, Disney+) a transformé la manière dont les utilisateurs découvrent les films. Ces plateformes reposent sur des systèmes de recommandation capables d’analyser les préférences et comportements pour proposer des contenus adaptés.
Le projet MovieLens Phase 4 vise à construire un moteur de recommandation intelligent à partir des fichiers ratings.csv, movies.csv et tags.csv, combinant analyse comportementale, segmentation non supervisée et filtrage collaboratif.


🎯 Objectifs du projet

Objectif général

Développer un système de recommandation de films fondé sur la segmentation des utilisateurs et la modélisation collaborative, afin d’améliorer la pertinence des suggestions.

Objectifs spécifiques

1. Analyser les comportements et les préférences des utilisateurs.


2. Identifier les genres les plus populaires et les mieux notés.


3. Segmenter les utilisateurs via l’algorithme KMeans.


4. Développer et comparer deux modèles : SVD et KNN.


5. Fournir des recommandations exploitables et personnalisées.



🧩 Méthodologie

Le projet suit la démarche analytique en 5 étapes :

1. Préparation des données :

Nettoyage, imputation et fusion des jeux de données.

Création de variables dérivées : main_genre, popularity.

2. Analyse exploratoire (EDA) :

Étude des distributions de notes et de la popularité par genre.

Corrélation entre activité et sévérité des utilisateurs.

Analyse qualitative des tags les plus utilisés.

3. Segmentation non supervisée (KMeans) :

Variables : moyenne des notes et volume d’activité.

Normalisation, sélection du nombre optimal de clusters, visualisation et interprétation.

Résultat : 5 profils utilisateurs distincts identifiés.

4. Modélisation avancée :

SVD (TruncatedSVD) : décomposition factorielle pour découvrir les préférences latentes.

KNN (User-Based) : filtrage collaboratif basé sur la similarité cosinus entre utilisateurs.

Évaluation par RMSE et MAE pour comparer la précision des modèles.

5. Recommandations stratégiques :

Recommandations ciblées selon le cluster d’utilisateur.

Perspectives d’amélioration et d’intégration d’un modèle hybride.



🧮 Jeux de données utilisés

Fichier	Description	Colonnes principales

movies.csv	Liste des films disponibles	movieId, title, genres
ratings.csv	Notes attribuées par les utilisateurs	userId, movieId, rating, timestamp
tags.csv	Étiquettes descriptives des utilisateurs	userId, movieId, tag, timestamp

Les fichiers ont été fusionnés autour de movieId pour créer une base cohérente et intégrée.


⚙ Outils et technologies

Langage : Python 3

Librairies principales : pandas, numpy, scikit-learn, matplotlib, seaborn

Modèles utilisés : TruncatedSVD, KNNBasic, KMeans

Environnement : Jupyter Notebook


📊 Résultats principaux

Modèles comparés

Modèle	RMSE	MAE	Interprétation

SVD (TruncatedSVD)	2.3626	1.9813	Bonne généralisation, mais moins précis.
KNN (User-Based)	1.4791	1.2559	Modèle plus fidèle et interprétable.


✅ KNN surpasse SVD en précision et en cohérence avec les notes réelles.

Segmentation (KMeans)

5 clusters identifiés :

1. Enthousiastes occasionnels


2. Exigeants réguliers


3. Généralistes


4. Sélectifs


5. Power users

Ces profils permettent d’adapter les recommandations selon le comportement de chaque groupe.



🧠 Interprétations essentielles

Les notes sont majoritairement comprises entre 3 et 4, traduisant une appréciation positive.

Les genres les plus notés sont Drame, Comédie et Action.

Les utilisateurs actifs se montrent plus modérés dans leurs notations.

Le KNN se démarque comme solution la plus performante pour une approche personnalisée et explicable.


🚀 Recommandations et perspectives

Techniques

Optimiser le SVD par régularisation et ajustement du nombre de composantes.

Tester des valeurs alternatives de k et de métriques de distance pour le KNN.

Étendre le jeu de données à MovieLens 1M ou Netflix Prize.


🚀Stratégiques

Déployer un tableau de bord interactif (Streamlit) pour visualiser les clusters et les performances.

Intégrer des variables contextuelles (date, popularité, acteurs) pour enrichir les recommandations.

Concevoir un modèle hybride (SVD + KNN) pour combiner précision et robustesse.


🧭 Enseignements clés

1. Méthodologiques : intégration réussie entre EDA, clustering et filtrage collaboratif.


2. Techniques : validation des modèles KMeans, SVD et KNN avec Scikit-learn.


3. Conceptuels : équilibre entre précision (KNN) et généralisation (SVD).

🏁 Conclusion

Le projet MovieLens Phase 4 a permis de démontrer qu’un système de recommandation basé sur le filtrage collaboratif peut être précis, explicable et évolutif.
Les résultats confirment la supériorité du KNN User-Based, tout en soulignant le potentiel d’un futur modèle hybride.
Ce travail constitue une référence méthodologique pour la conception de moteurs de recommandation modernes, centrés sur l’utilisateur et fondés sur la donnée.
