# Configuration de l'API et Paramètres de l'Application

Ce document détaille la configuration de l'API externe et les paramètres de base de l'application Momentrix NBA Analytics.

## Configuration de l'API

L'application utilise l'API NBA de RapidAPI comme source principale de données. Pour configurer l'accès à cette API, les paramètres suivants doivent être définis dans le fichier `.env` à la racine du projet :

```
# API Configuration
RAPIDAPI_KEY=af4655b88bmsh391d0acc20099abp1f2b73jsn67367e097c0a
RAPIDAPI_HOST=api-nba-v1.p.rapidapi.com
```

### Détails de l'API

- **Fournisseur** : RapidAPI
- **Nom de l'API** : API-NBA-v1
- **URL de base** : https://api-nba-v1.p.rapidapi.com
- **Documentation** : Disponible sur le portail RapidAPI

### Endpoints Principaux

L'application utilise les endpoints suivants :

| Endpoint | Description | Paramètres clés |
|----------|-------------|-----------------|
| `/games` | Récupération des matchs | `date`, `season`, `team` |
| `/teams` | Informations sur les équipes | `league`, `season` |
| `/players` | Informations sur les joueurs | `team`, `season` |
| `/statistics` | Statistiques des matchs | `game`, `player`, `team` |
| `/standings` | Classements des équipes | `league`, `season` |

### Gestion des quotas

L'API RapidAPI impose des limites d'utilisation. Pour optimiser l'utilisation des quotas, l'application implémente les stratégies suivantes :

1. **Mise en cache systématique** : Les données sont mises en cache pendant 24 heures par défaut
2. **Extractions groupées** : Les données sont extraites par lots pour réduire le nombre d'appels
3. **Planification intelligente** : Les extractions sont programmées durant les heures creuses

## Paramètres de l'Application

Les paramètres généraux de l'application sont également définis dans le fichier `.env` :

```
# Application Settings
DEBUG=True
DATABASE_PATH=data/db/momentrix.db
CACHE_TIMEOUT=86400
```

### Description des paramètres

- **DEBUG** : Mode de débogage (True/False)
  - En mode DEBUG=True, l'application affiche des logs détaillés et des informations de débogage
  - En production, ce paramètre doit être défini à False
  
- **DATABASE_PATH** : Chemin vers le fichier de base de données SQLite
  - Ce chemin est relatif à la racine du projet
  - La base de données sera créée automatiquement si elle n'existe pas
  
- **CACHE_TIMEOUT** : Durée de validité du cache en secondes
  - La valeur par défaut (86400) correspond à 24 heures
  - Cette durée peut être ajustée selon les besoins de fraîcheur des données

## Configuration pour le développement

Pour configurer l'environnement de développement, suivez ces étapes :

1. Créez un fichier `.env` à la racine du projet
2. Copiez les paramètres ci-dessus dans ce fichier
3. Ajustez les valeurs selon votre environnement
4. Assurez-vous que le fichier `.env` est ignoré par Git (via `.gitignore`)

Exemple de configuration complète pour le développement :

```
# API Configuration
RAPIDAPI_KEY=af4655b88bmsh391d0acc20099abp1f2b73jsn67367e097c0a
RAPIDAPI_HOST=api-nba-v1.p.rapidapi.com

# Application Settings
DEBUG=True
DATABASE_PATH=data/db/momentrix.db
CACHE_TIMEOUT=86400

# Development Settings
FLASK_ENV=development
FLASK_DEBUG=1
FLASK_APP=app/main.py
```

## Sécurité et bonnes pratiques

- Ne partagez jamais votre clé API RapidAPI
- N'incluez pas le fichier `.env` dans les dépôts publics
- Utilisez des variables d'environnement pour les déploiements en production
- Surveillez votre utilisation des quotas API pour éviter les interruptions de service

Ces paramètres de configuration permettent d'adapter facilement l'application à différents environnements tout en maintenant la sécurité des informations sensibles.