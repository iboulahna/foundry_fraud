# foundry_fraud


Ingestion des données via Foundry Data Catalog

Collecte des transactions bancaires et des données clients.

Stockage des données dans le Data Catalog pour un accès unifié.

Feature Engineering avec Foundry Code Workbook

Nettoyage et transformation des données (montant, fréquence des transactions, utilisation de plusieurs cartes bancaires, etc.).

Calcul de nouvelles variables pertinentes pour la détection de fraude.

Entraînement du modèle avec Foundry ML + MLflow

Entraînement d'un modèle LightGBM/XGBoost sur les features transformées.

Utilisation de MLflow pour suivre les expérimentations et sauvegarder les hyperparamètres.

Stockage et versioning du modèle dans MLflow

Enregistrement du modèle avec ses performances et métriques.

Comparaison avec les modèles précédents pour décider du déploiement.

Déploiement du modèle avec Foundry API Services

Exposition du modèle via une API REST pour une intégration dans les systèmes de détection de fraude.

Scalabilité et gestion des requêtes en temps réel.

Monitoring des performances via MLflow Metrics

Suivi des précisions du modèle sur des données réelles.

Comparaison avec les performances passées pour identifier toute dégradation.

Détection de Drift avec Evidently AI

Analyse des distributions des variables et des performances du modèle.

Génération de rapports de drift pour identifier les variations significatives des données.

Réentraînement automatique si drift détecté avec Foundry Workflow

Si un drift est détecté, un pipeline Foundry est déclenché pour réentraîner un modèle.

Automatisation de l’évaluation et du déploiement du nouveau modèle si amélioration.
