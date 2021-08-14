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
[Slides](https://docs.google.com/presentation/d/1ttM1pxhvZ5AhgW1_1CAfIMsCXi-a3zxtHxyUmShknHc/edit?usp=sharing)

# Conclusion

Nous avons pu trouver plusieurs modèles qui ont des résultats limités, en effet le F1 scoring / recall ne dépassent pas 0.3. Nous voyons sur les matrices de confusion que les cas "CHURNED" sont en très faibles quantité et n'arrivent pas à être prédits correctement contrairement aux personnes qui sont encore présentes dans leurs entreprises.

# Aller plus loin

- Obtenir le reste des données pour augmenter fortement la taille du dataset : la proportion train/test modifiait beaucoup les résultats de scoring. Il faudrait contacter l'entreprise à l'origine de ces données 
- Recommencer l’analyse des datasets avec une autre approche
- Continuer à chercher des meilleurs modèles et les meilleurs paramètres associés pour optimiser les résultats

