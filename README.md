# Liens entre l'activité, bonheur et turnover des employés

## Pouvons nous prédire si un employé va démissionner en fonction de son activité quotidienne ainsi que le contenu de ses messages ?



*Mathieu Guarino*

*[Iron Hack, DataAnalyze & 14/08/2021]*

## Content
- [Project Description](#project-description)
- [Hypothèses / Questions](#hypotheses-/-questions)
- [Dataset](#dataset)
- [Workflow](#workflow)
- [Liens](#liens)

<a name="project-description"></a>

## Description du projet
Le projet est composé de 4 datasets :
- La présence ou non des employés avec leur dernière activité
- L'intéraction d'un employé vis à vis d'un commentaire (s'il à like ou dislike le commentaire)
- Le vote récurent et daté d'un employé avec son niveau de bonheur (de 1 à 4)
- Les commentaires anonymisés et datés d'un employé, avec le nombre et like, dislike reçus


<a name="hypotheses-/-questions"></a>

## Hypothèses / Questions :
- Est-ce que les employés non actifs sont ceux qui partent le plus ?
- Y a t'il une différence flagrante de bonheur en fonction des entreprises ? 
- Est-ce possible de prédire le départ d'un employé ?

<a name="dataset"></a>

## Dataset
Les datasets proviennent de :
[Daily Happiness & Employee Turnover](https://www.kaggle.com/harriken/employeeturnover)


<a name="workflow"></a>

## Workflow
Les données étaient plutôt bien agencées et facile à exploiter, peu de valeurs manquantes. Il y a eu des conversions de certaines colonnes en format date ordinal. 
La première difficulté était de déterminer comment lier les 4 datasets avec uniquement les informations pertinentes, il s'est avéré que le dataframe final comportait peu de colonnes : il y a donc eu un travail supplémentaire pour rajouter des colonnes pour aider au machine learning :

- Une image de fréquence d'activité d'un utilisateur entre deux commentaire a été rajouté via la somme des différences entre la date de deux commentaires
- Savoir si l'utilisateur à like le commentaire d'une personne qui n'est plus présente 
- L'évolution des votes d'un utilisateur via le calcul d'une pente

Il faut faire cependant attention à plusieurs biais : 
- Plus une personne est présente, plus son nombre de vote devrait être important
- Des personnes peuvent partir de l'entreprise sans en être mécontent



<a name="links"></a>

## Liens

[Repository](https://github.com/screamzz/FinalProjectIronHack/)   
[Slides](https://docs.google.com/presentation/d/1S--k2ATpx7-ZB8DW-CKB1UwcDBGFnogNY7cCvO14OKQ/edit?usp=sharing)

# Conclusion

Nous avons pu trouver plusieurs modèles qui semblent efficaces sur les scores, cependant quand nous creusont un peu plus avec des résultats de précisions, courbes de rappel, courbes ROC et matrice de confusion, nous trouvons que les résultats semblent peu satisfaisant avec 

# Aller plus loin

Nous avons à peine éffleuré la partie visible du dataset, nous pouvons en effet creuser et voir si la qualité de la voiture et l'évolution des normes de pollution automobile influencent les émissions de gaz. Les données les plus récentes datent de 2015, les véhicules hybrides et 100% électriques n'étaient pas très présents sur le parc automobile, c'est pour ça que nous les avons retirés de nos données d'entrées, mais il serait intéressant de voir l'effet de l'hybride sur les gaz et si le gain vaut l'utilisation de matière premières pour la réalisation de la batterie électrique.
