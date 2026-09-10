# ChurnLens

Analyse et prédiction de l'attrition client chez Expresso Sénégal — méthodologie CRISP-DM
complète, comparaison rigoureuse de modèles et métriques adaptées au déséquilibre des classes.

## Le projet

Le désabonnement (churn) coûte cher aux opérateurs télécoms : chaque client perdu représente un
revenu récurrent envolé, souvent plus coûteux à remplacer qu'à retenir. Ce projet analyse les
facteurs qui poussent les clients d'Expresso Sénégal à se désabonner, et construit un modèle
capable de les identifier à l'avance pour permettre une action de rétention ciblée.

## Ce que couvre le notebook

- **Méthodologie CRISP-DM** complète : compréhension métier → données → préparation →
  modélisation → évaluation → déploiement
- **Analyse exploratoire approfondie** : univariée, bivariée, multivariée, avec tests
  statistiques (Pearson, Khi², ANOVA) pour valider les relations entre variables
- Nettoyage de données rigoureux (valeurs manquantes, doublons)
- **Comparaison de 3 modèles** (régression logistique, arbre de décision, Random Forest) par
  validation croisée stratifiée
- **Optimisation d'hyperparamètres** (`RandomizedSearchCV`)
- Évaluation adaptée au déséquilibre des classes (~81% loyaux / ~19% désabonnés) : ROC-AUC,
  Average Precision (PR-AUC), matrice de confusion, courbes ROC et Précision-Rappel
- Interprétabilité (importance des variables) et **ajustement du seuil de décision**
- Recommandations business actionnables (tarification, fidélisation, campagnes ciblées)

## Point clé méthodologique

Sur un problème déséquilibré, l'accuracy — et le F1-score en moyenne `micro`, qui lui est
mathématiquement équivalent — peuvent masquer un modèle en réalité peu utile : un score global
élevé peut cacher un rappel très faible sur la classe qui compte le plus (les clients qui vont
réellement se désabonner). Ce projet illustre concrètement ce piège et montre comment le corriger
via des métriques adaptées (ROC-AUC, PR-AUC) et un ajustement du seuil de décision.

## Lancer le notebook

```bash
pip install -r requirements.txt
jupyter notebook PROJET_METHODES_DE_CLASSIFICATION_.ipynb
```

## Source des données

Expresso Churn Prediction Challenge — données clients d'Expresso Sénégal (opérateur de
télécommunications), publiées dans le cadre d'un challenge de prédiction de l'attrition.
