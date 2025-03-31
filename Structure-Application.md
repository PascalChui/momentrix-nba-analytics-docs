# Structure de l'Application Momentrix NBA Analytics

Ce document détaille l'architecture de fichiers et dossiers de l'application Momentrix NBA Analytics, fournissant une vue d'ensemble de l'organisation du code et des ressources.

```
C:\NBA predictions\
│
├── app/                      # Code source principal de l'application
│   ├── api/                  # Module d'intégration API
│   │   ├── __init__.py
│   │   ├── client.py         # Client API principal
│   │   └── models.py         # Modèles de données API
│   │
│   ├── analysis/             # Algorithmes d'analyse
│   │   ├── __init__.py
│   │   ├── quarters.py       # Analyse des écarts par quart-temps
│   │   ├── trends.py         # Analyse des tendances
│   │   ├── badges.py         # Logique d'attribution des badges
│   │   └── predictions.py    # Modèles prédictifs
│   │
│   ├── data/                 # Gestion des données
│   │   ├── __init__.py
│   │   ├── database.py       # Interface de base de données
│   │   ├── models.py         # Modèles de données applicatifs
│   │   └── cache.py          # Système de mise en cache
│   │
│   ├── services/             # Services applicatifs
│   │   ├── __init__.py
│   │   ├── team_service.py   # Service de gestion des équipes
│   │   ├── player_service.py # Service de gestion des joueurs
│   │   └── game_service.py   # Service de gestion des matchs
│   │
│   ├── web/                  # Interface utilisateur web
│   │   ├── static/           # Ressources statiques
│   │   │   ├── css/          # Feuilles de style
│   │   │   ├── js/           # Scripts JavaScript
│   │   │   └── images/       # Images et ressources graphiques
│   │   │
│   │   ├── templates/        # Templates HTML
│   │   │   ├── base.html     # Template de base
│   │   │   ├── dashboard/    # Templates pour le tableau de bord
│   │   │   ├── teams/        # Templates pour les équipes
│   │   │   ├── players/      # Templates pour les joueurs
│   │   │   └── predictions/  # Templates pour les prédictions
│   │   │
│   │   ├── __init__.py
│   │   ├── routes.py         # Définition des routes
│   │   └── forms.py          # Formulaires web
│   │
│   ├── __init__.py           # Initialisation de l'application
│   ├── config.py             # Configuration de l'application
│   └── main.py               # Point d'entrée principal
│
├── tests/                    # Tests automatisés
│   ├── __init__.py
│   ├── test_api.py
│   ├── test_analysis.py
│   └── test_predictions.py
│
├── data/                     # Stockage des données
│   ├── cache/                # Cache des données API
│   └── db/                   # Fichiers de base de données
│
├── logs/                     # Journaux d'application
│
├── docs/                     # Documentation
│   ├── api/                  # Documentation API
│   └── user/                 # Guide utilisateur
│
├── .env                      # Variables d'environnement (clés API, etc.)
├── requirements.txt          # Dépendances Python
├── README.md                 # Documentation générale
└── run.py                    # Script de lancement
```

## Description des Composants Principaux

### Module API

Ce module gère toutes les interactions avec l'API NBA externe. Il assure l'authentification, le formatage des requêtes et la transformation des réponses en modèles de données utilisables par l'application.

- **client.py** : Client d'API qui encapsule les appels HTTP et gère les erreurs
- **models.py** : Définition des structures de données qui reflètent les réponses de l'API

### Module Analysis

Ce module contient tous les algorithmes analytiques qui constituent le cœur de l'application. Il transforme les données brutes en insights actionnables.

- **quarters.py** : Implémente l'analyse par quart-temps, pilier de la méthodologie Momentrix
- **trends.py** : Détection et analyse des tendances à travers les matchs
- **badges.py** : Système d'attribution des badges basé sur les critères définis
- **predictions.py** : Modèles prédictifs pour les résultats des matchs

### Module Data

Ce module s'occupe de la persistance et de la gestion des données, fournissant une interface unifiée pour l'accès aux données, qu'elles proviennent de l'API ou de la base de données locale.

- **database.py** : Interface avec la base de données SQLite
- **models.py** : Modèles ORM pour représenter les entités dans la base de données
- **cache.py** : Mécanisme de mise en cache pour optimiser les performances

### Module Services

Ce module implémente la logique métier de l'application, servant d'intermédiaire entre la couche données et l'interface utilisateur.

- **team_service.py** : Gestion des équipes et de leurs statistiques
- **player_service.py** : Gestion des joueurs et de leur impact
- **game_service.py** : Gestion des matchs, prédictions et analyses

### Module Web

Ce module contient toute l'interface utilisateur web, organisée selon le modèle MVC (Modèle-Vue-Contrôleur).

- **routes.py** : Définition des endpoints HTTP et de la logique de routage
- **forms.py** : Validation et traitement des formulaires
- **templates/** : Vues HTML utilisant Jinja2 pour le rendu dynamique
- **static/** : Ressources statiques (CSS, JavaScript, images)

## Considérations Architecturales

- **Séparation des préoccupations** : Chaque module a une responsabilité claire et bien définie
- **Structure modulaire** : Facilite la maintenance et les tests unitaires
- **Extensibilité** : L'architecture permet d'ajouter facilement de nouveaux composants
- **Dépendances minimales** : Les modules sont conçus pour minimiser les interdépendances

Cette structure de projet reflète les meilleures pratiques de développement Python et assure une base solide pour le développement et l'évolution de l'application Momentrix NBA Analytics.