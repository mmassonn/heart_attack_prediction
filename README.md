# Prédiction du risque d’infartus à partir des données cliniques

Les maladies cardio-vasculaires sont selon l'organisation mondiale de la santé, la première cause de mortalité dans le monde. En effet on estime à 17,7 millions le nombre de décès imputables aux maladies cardio-vasculaires, soit 31% de la mortalité mondiale totale (7,4 millions sont dus à une cardiopathie coronarienne et 6,7 millions à un AVC). 

Aujourd'hui il est possible de prévenir la plupart des maladies cardiovasculaires en s’attaquant à l’aide de stratégies (à l’échelle de la population) aux facteurs de risque comportementaux comme le tabagisme, la mauvaise alimentation, l'obésité, la sédentarité et l'utilisation nocive de l’alcool.

C'est pourquoi les personnes souffrant de maladies cardiovasculaires ou exposées à un risque élevé de maladies cardiovasculaires (du fait de la présence d’un ou plusieurs facteurs de risque comme l’hypertension, le diabète, l’hyperlipidémie ou une maladie déjà installée) nécessitent une détection précoce et une prise en charge comprenant soutien psychologique et médicaments, selon les besoins.

Ce projet de développement d'un outils de prédiction du risque d’infartus à partir des données cliniques s'inscrit dans cette démarche d'aide médicale au diagnostique.

### Base de données

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

### Objectif

Je choisi l'indice de concordance comme métrique d'évaluation. L'indice de concordance ou c-index est défini comme la proportion de paires concordantes divisée par le nombre total de paires d'évaluation possibles.
