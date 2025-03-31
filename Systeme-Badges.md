# Système de Badges de Momentrix NBA Analytics

Ce document détaille le système de badges utilisé dans l'application Momentrix NBA Analytics, une fonctionnalité distinctive qui permet de caractériser les performances et les comportements des équipes de manière intuitive et visuelle.

## Concept et Objectif

Le système de badges a été conçu pour traduire des analyses statistiques complexes en indicateurs visuels facilement compréhensibles. Ces badges permettent aux utilisateurs d'identifier rapidement les forces, faiblesses et caractéristiques distinctives de chaque équipe sans avoir à interpréter des tableaux statistiques détaillés.

Chaque badge représente un aspect particulier de la performance d'une équipe, déterminé par des critères statistiques précis et mesurables. Les badges sont attribués de manière dynamique, reflétant l'évolution des performances au cours de la saison.

## Catégories de Badges

Les badges sont organisés en quatre catégories principales, chacune mettant en lumière un aspect différent de la performance des équipes.

### Badges Offensifs

Ces badges caractérisent les capacités offensives des équipes.

| Badge | Couleur | Description | Critères d'attribution |
|-------|---------|-------------|------------------------|
| **SCORER** | Rouge (#DC3545) | Équipe à forte capacité offensive | Dépasse 25 points par quart-temps dans plus de 60% des cas |
| **FAST BREAK** | Orange (#FD7E14) | Équipe efficace en contre-attaque | Plus de 15 points en contre-attaque par match en moyenne |
| **OFFENSIVE** | Bleu clair (#17A2B8) | Équipe orientée vers l'attaque | Ratio points marqués/encaissés > 1.1 sur les 15 derniers matchs |

### Badges Défensifs

Ces badges identifient les équipes qui excellent en défense.

| Badge | Couleur | Description | Critères d'attribution |
|-------|---------|-------------|------------------------|
| **DEFENSIVE** | Orange (#F7931E) | Équipe à défense solide | Limite les adversaires à moins de 20 points par quart-temps dans plus de 50% des cas |
| **SOLID** | Bleu clair (#17A2B8) | Équipe à défense consistante | Maintient un différentiel défensif positif dans plus de 70% des quart-temps |
| **RESISTANT** | Violet (#6610F2) | Équipe difficile à dominer | Ne perd jamais par plus de 15 points d'écart |

### Badges de Comportement

Ces badges caractérisent le comportement et la stabilité des équipes.

| Badge | Couleur | Description | Critères d'attribution |
|-------|---------|-------------|------------------------|
| **CONSISTENT** | Vert (#28A745) | Équipe aux performances stables | Écart-type de performance inférieur à 5 points entre quart-temps |
| **OVERTURNER** | Bleu marine (#1A365D) | Équipe capable de renverser des situations | Remporte au moins 30% de ses matchs après avoir été menée de 10 points ou plus |
| **DISAPPOINTMENT** | Gris (#6C757D) | Équipe aux performances inférieures aux attentes | Performances significativement inférieures aux prévisions basées sur le classement |
| **STREAKY** | Gris (#6C757D) | Équipe aux performances irrégulières | Enchaîne des séries de victoires et de défaites (plus de 3 consécutives) |

### Badges Situationnels

Ces badges mettent en évidence des comportements dans des situations spécifiques.

| Badge | Couleur | Description | Critères d'attribution |
|-------|---------|-------------|------------------------|
| **CLUTCH** | Turquoise (#20C997) | Équipe performante dans les moments décisifs | Différentiel positif dans les 5 dernières minutes des matchs serrés |
| **HOME FORCE** | Bleu (#007BFF) | Équipe dominante à domicile | Gagne plus de 70% de ses matchs à domicile |
| **UNDERDOG** | Rose (#E83E8C) | Équipe performante en tant qu'outsider | Remporte plus de 40% de ses matchs en tant que non-favori |

## Mécanisme d'Attribution

Le processus d'attribution des badges suit une méthodologie rigoureuse en trois étapes :

### 1. Évaluation continue

- Les performances de chaque équipe sont analysées après chaque match
- Les statistiques pertinentes sont mises à jour et comparées aux seuils d'attribution
- Une fenêtre glissante des 20 derniers matchs est utilisée pour la plupart des critères

### 2. Confirmation progressive

- Un badge n'est pas attribué immédiatement après avoir atteint les critères
- Un système de "points de confirmation" accumule la conformité aux critères
- Le badge est attribué lorsque le seuil de confirmation est atteint (généralement 3-5 matchs consécutifs)

### 3. Règles de déchéance

- Les badges ne sont pas permanents (sauf exception)
- Un système similaire de "points de déchéance" s'accumule lorsque les critères ne sont plus remplis
- Le badge est retiré lorsque le seuil de déchéance est atteint

## Visualisation dans l'Interface

Les badges sont intégrés de manière cohérente dans l'interface utilisateur :

- **Page d'accueil** : Affichage des badges récemment attribués
- **Page des équipes** : Vue d'ensemble des badges attribués à chaque équipe
- **Page de détail d'équipe** : Section dédiée expliquant les badges et leur justification
- **Page des badges** : Vue complète permettant de filtrer les équipes par badge

Chaque badge est représenté par une pastille colorée avec un texte concis, utilisant un code couleur cohérent à travers l'application pour faciliter la reconnaissance visuelle.

## Impact sur les Prédictions

Les badges ne sont pas seulement des indicateurs visuels, ils sont également intégrés au modèle prédictif :

- Certains badges modifient les probabilités de base calculées par le modèle
- Les combinaisons spécifiques de badges peuvent révéler des compatibilités ou incompatibilités entre styles de jeu
- L'historique d'attribution et de retrait des badges est utilisé pour identifier les tendances émergentes

Par exemple, une équipe avec le badge "CLUTCH" verra sa probabilité de victoire augmentée dans les prédictions de matchs serrés, tandis qu'une équipe avec le badge "HOME FORCE" bénéficiera d'un avantage supplémentaire pour les matchs à domicile.

## Personnalisation et Configuration

Les administrateurs peuvent personnaliser le système de badges via la page de configuration :

- Ajustement des seuils d'attribution pour chaque badge
- Modification des règles de confirmation et de déchéance
- Création de badges personnalisés pour des analyses spécifiques
- Configuration de l'impact des badges sur le modèle prédictif

Cette flexibilité permet d'adapter le système aux spécificités de chaque saison et d'améliorer continuellement la précision des caractérisations.

## Conclusion

Le système de badges constitue un élément différenciateur majeur de Momentrix NBA Analytics, transformant des analyses statistiques complexes en insights visuels immédiatement compréhensibles. Cette approche facilite l'identification des tendances, forces et faiblesses des équipes, tout en enrichissant le modèle prédictif avec des caractérisations comportementales pertinentes.