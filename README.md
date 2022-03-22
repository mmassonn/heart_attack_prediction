# Prédiction du risque de développement d'une cardiopathie

Veuillez trouver ci-dessus :

-le fichier "breast_cancer_analyse.ipynb" dans lequel j'analyse le jeu de données;

-le fichier "breast_cancer_prediction.ipynb" où je mets en place un modèle de Machine Learning;

-le fichier "breast_cancer_prediction_tuning.ipynb" dans lequel j'optimise les hyperparamètres du modèle ayant obtenu le meilleur score F1. Dans notre cas il s'agit du modèle RandomForest.


### Contexte

Les maladies cardiovasculaires sont selon l'Organisation Mondiale de la Santé, la première cause de mortalité dans le monde. On estime à 17,7 millions le nombre de décès imputables aux maladies cardiovasculaires, soit 31% de la mortalité mondiale totale (7,4 millions sont dus à une cardiopathie coronarienne et 6,7 millions à un AVC). 

Aujourd'hui il est possible de prévenir la plupart des maladies cardiovasculaires en prenant garde (à l’échelle de la population) aux facteurs de risque comportementaux comme le tabagisme, une mauvaise alimentation, l'obésité, la sédentarité et l'utilisation nocive de l’alcool.

C'est pourquoi une détection précoce et une prise en charge sont néessaires chez les personnes souffrant de maladies cardiovasculaires ou exposées à un risque élevé de développer une maladie cardiovasculaire. 

L'objectif de ce projet est de mettre en place un outil nous permettant de prédire le risque de développer une cardiopathie. Il s'inscrit dans une démarche d'aide médicale au diagnostique mais n'ayant pas été validé par des experts, il ne doit pas être utilisé à des fins médicales.

### Base de données (918 patients, 11 caractéristiques + 1 cible)

Ce jeu de données a été créé en combinant différents jeux de données déjà disponibles indépendamment mais non combinés auparavant. Dans cet ensemble de données, 5 jeux de données cardiaques sont combinés sur 11 caractéristiques communes, ce qui en fait le plus grand ensemble de données sur les maladies cardiaques disponible à ce jour à des fins de recherche. 

Les cinq ensembles de données utilisés pour sa conservation sont :

Cleveland : 303 observations
Hongrois : 294 observations
Suisse : 123 observations
Long Beach Virginie : 200 observations
Ensemble de données Stalog (cœur): 270 observations
Total : 1190 observations
Dupliqué : 272 observations

Cela donne un ensemble de données final de 918 observations.

Chaque ensemble de données utilisé peut être trouvé sous l'index des ensembles de données sur les maladies cardiaques de l'UCI Machine Learning Repository sur le lien suivant : https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/

fedesoriano. (September 2021). Heart Failure Prediction Dataset. Retrieved [Date Retrieved] from https://www.kaggle.com/fedesoriano/heart-failure-prediction.

Createurs:

Hungarian Institute of Cardiology. Budapest: Andras Janosi, M.D.
University Hospital, Zurich, Switzerland: William Steinbrunn, M.D.
University Hospital, Basel, Switzerland: Matthias Pfisterer, M.D.
V.A. Medical Center, Long Beach and Cleveland Clinic Foundation: Robert Detrano, M.D., Ph.D.

Donateur: David W. Aha (aha '@' ics.uci.edu) (714) 856-8779

### Choix de la métrique

Je choisis le score F1 comme métrique d'évaluation. Il permet de résumer les valeurs de la précision et de la sensiblité en une seule métrique. Dans mon cas, la précision me permet d'être certain que lorsque l'agorithme prédit une cardiopathie, le patient a réelement cette pathologie. Et la sensibilité me permet de détecter le maximum de cardiopathies dans la population qui en est atteinte.

### Choix du modèle

En Machine Learning, les méthodes ensemblistes consistent à mettre en commun plusieurs algorithmes de Machine Learning affichant une performance modérée, afin d'obtenir des prédictions de meilleures qualités. 

Ici j'essaie trois types de méthodes différentes :

1) Le bagging (BaggingClassifier), aussi appelé bootstrap aggregating, consiste à entraîner plusieurs algorithmes de Machine Learning sur différents jeux de données. Ces derniers provenant du jeu de données originale, chaque algorithme observe sous un angle unique les données. Puis, lors de la prédiction globale on effectue un vote à la majorité pour la classification.

2) La forêt aléatoire (RandomForestClassifier) est une amélioration du bagging, qui est associée au concept de sous-espace aléatoire, et qui s’attache à créer de multiples arbres de décision pour l’apprentissage, avec des modèles entraînés sur des sous-ensembles de données légèrement différents. Comme les échantillons sont créés de manière aléatoire, la corrélation entre les arbres est réduite, et on obtient un meilleur résultat à la fin.

3) Le boosting (AdaBoostClassifier) va quant à lui combiner les modèles classifieurs en les pondérant à chaque nouvelle prédiction, de façon à ce que les modèles ayant prédit correctement les fois précédentes aient un poids plus important que les modèles incorrects. Mieux un modèle classe, plus il devient important au fil du temps.
