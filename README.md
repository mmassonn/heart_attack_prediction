# Prédiction du développement d'une cardiopathie à partir des données cliniques

L'objectif de ce projet est le développement d'un outils de prédiction du risque de développer une cardiopathie à partir des données cliniques. Ce projet s'inscrit dans une démarche d'aide médicale au diagnostique mais n'ayant pas été validé, il ne doit pas être utilisé à des fins médicales. 

Vous pouvez trouver ci-dessus deux fichiers .ipynb. Le fichier "heart_attack_analyse.ipynb" réalise une analyse stastistique du jeu de données et le fichier "heart_attack_prediction.ipynb" met en place un modèle de machine learning. Le fichier "heart_attack_prediction_tuning.ipynb" optimise l'algorithme ayant obtenu le meilleur F1 score : RandomForest.

### Contexte

Les maladies cardio-vasculaires sont selon l'organisation mondiale de la santé, la première cause de mortalité dans le monde. En effet on estime à 17,7 millions le nombre de décès imputables aux maladies cardio-vasculaires, soit 31% de la mortalité mondiale totale (7,4 millions sont dus à une cardiopathie coronarienne et 6,7 millions à un AVC). 

Aujourd'hui il est possible de prévenir la plupart des maladies cardiovasculaires en s’attaquant à l’aide de stratégies (à l’échelle de la population) aux facteurs de risque comportementaux comme le tabagisme, la mauvaise alimentation, l'obésité, la sédentarité et l'utilisation nocive de l’alcool.

C'est pourquoi les personnes souffrant de maladies cardiovasculaires ou exposées à un risque élevé de maladies cardiovasculaires (du fait de la présence d’un ou plusieurs facteurs de risque comme l’hypertension, le diabète, l’hyperlipidémie ou une maladie déjà installée) nécessitent une détection précoce et une prise en charge comprenant soutien psychologique et médicaments, selon les besoins.

### Base de données (License : CC BY-NC-SA 4.0)

Ce jeu de données a été créé en combinant différents jeux de données déjà disponibles indépendamment mais non combinés auparavant. Dans cet ensemble de données, 5 ensembles de données cardiaques sont combinés sur 11 caractéristiques communes, ce qui en fait le plus grand ensemble de données sur les maladies cardiaques disponible à ce jour à des fins de recherche. Les cinq ensembles de données utilisés pour sa conservation sont :

Cleveland : 303 observations
Hongrois : 294 observations
Suisse : 123 observations
Long Beach Virginie : 200 observations
Ensemble de données Stalog (cœur): 270 observations
Total : 1190 observations
Dupliqué : 272 observations

Ensemble de données final : 918 observations

Chaque ensemble de données utilisé peut être trouvé sous l'index des ensembles de données sur les maladies cardiaques de l'UCI Machine Learning Repository sur le lien suivant : https://archive.ics.uci.edu/ml/machine-learning-databases/heart-disease/

fedesoriano. (September 2021). Heart Failure Prediction Dataset. Retrieved [Date Retrieved] from https://www.kaggle.com/fedesoriano/heart-failure-prediction.

Createurs:

Hungarian Institute of Cardiology. Budapest: Andras Janosi, M.D.
University Hospital, Zurich, Switzerland: William Steinbrunn, M.D.
University Hospital, Basel, Switzerland: Matthias Pfisterer, M.D.
V.A. Medical Center, Long Beach and Cleveland Clinic Foundation: Robert Detrano, M.D., Ph.D.

Donateur: David W. Aha (aha '@' ics.uci.edu) (714) 856-8779

### Métrique

Ici, je choisi le score F1 comme métrique d'évaluation. Cette dernière permet de résumer les valeurs de la précision et de la sensiblité en une seule métrique. Dans l'analyse statistique de la classification binaire, c'est une mesure de la précision d'un test. Il est calculé à partir de la précision et de la sensiblité du test, où la précision est le nombre de vrais résultats positifs divisé par le nombre de tous les résultats positifs, y compris ceux qui ne sont pas identifiés correctement, et la sensiblité est le nombre de vrais résultats positifs divisé par le nombre de tous les échantillons qui auraient dû être identifiés comme positifs. 

### Modèle

En machine learning, la méthode ensembliste consiste à utiliser plusieurs algorithmes d'apprentissage automatique, en les mettant en commun pour obtenir des prédictions de meilleure qualité. 

Le bagging (BaggingClassifier), aussi appelé bootstrap aggregating, consiste à sous-échantillonner les données, en créant un data set pour chaque modèle (mais similaire à l’original). Puis, lors de la combinaison, on effectue l’analyse prédictive au travers d’un vote à la majorité pour la classification, ou en moyennant pour la régression.

La forêt aléatoire (RandomForestClassifier) est une amélioration du bagging, qui est associé au concept de sous-espace aléatoire, et qui s’attache à créer de multiples arbres de décision pour l’apprentissage, avec des modèles entraînés sur des sous-ensembles de données légèrement différents. Vu que les échantillons sont créés de manière aléatoire, la corrélation entre les arbres est réduite, et on obtient un meilleur résultat à la fin. Cette méthode est de nos jours très utilisée par les data scientists.

Le boosting (AdaBoostClassifier) va lui combiner les modèles classifieurs en les pondérant à chaque nouvelle prédiction, de façon à ce que les modèles ayant prédit correctement les fois précédentes aient un poids plus important que les modèles incorrects. Mieux un modèle classe, plus il devient important au fil du temps.
