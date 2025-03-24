# MLOps Architecture – Détection de Fraude dans Palantir Foundry

Ce document présente le **schéma de l'architecture MLOps** conçu pour un cas d’usage de **détection de fraude** en environnement **Palantir Foundry**.

---

### 1. Ingestion des données via Foundry Data Catalog

- Collecte des **transactions bancaires** et des **données clients**.
- Stockage dans le **Data Catalog** pour assurer un accès unifié et sécurisé.

### 2. Feature Engineering avec Foundry Code Workbook

- Nettoyage et transformation des données :  
  → Montants, fréquence des transactions, multi-cartes, etc.  
- Création de **nouvelles variables** pertinentes pour détecter les comportements frauduleux.

### 3. Entraînement du modèle avec Foundry ML + MLflow

- Modélisation avec **LightGBM/XGBoost** sur les features transformées.
- Suivi des expérimentations et gestion des hyperparamètres via **MLflow**.

### 4. Versioning et stockage du modèle dans MLflow

- Enregistrement du modèle avec ses **performances et métriques clés**.
- Comparaison automatique avec les versions précédentes pour guider les décisions de déploiement.

### 5. Déploiement du modèle via Foundry API Services

- Mise à disposition du modèle via une **API REST**.
- Intégration facile avec les systèmes de détection de fraude en production.
- Support de la **scalabilité** et des **requêtes temps réel**.

### 6. Monitoring des performances avec MLflow Metrics

- Suivi continu des **performances sur données réelles**.
- Comparaison avec l'historique pour identifier toute **dégradation** du modèle.

### 7. Détection de Drift avec Evidently AI

- Analyse de la dérive des données (features, performance).
- **Rapports automatiques** pour identifier les changements significatifs.

### 8. Réentraînement automatique avec Foundry Workflow

- Si un drift est détecté, déclenchement d’un **pipeline automatisé** :
  - Réentraînement du modèle.
  - Évaluation des performances.
  - Déploiement automatique si le nouveau modèle est meilleur.
