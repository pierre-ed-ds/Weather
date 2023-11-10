# Météo Montpellier
## Objectif

Le but de ce site est d'afficher les prévisions météo de Montpellier sur un intervalle de cinq jours.

## Site web Quarto

Il est possible de consulter mon site sous l'adresse suivante: [pierre-ed-ds.github.io/Weather](https://pierre-ed-ds.github.io/Weather/). 
Ce site a été deployé avec github pages et s'actualise automatiquement toutes les heures. 

## Méthodologie

* Avec `Quarto`, il est possible de créer un site efficacement en y intégrant du code. J'ai donc basé la plupart de mon code sur python.
* Tout d'abord, en utilisant le module `datetime` il est possible de récupérer la date actuelle et de modifier l'URL de l'API avec les dates qui nous intéressent.
* Après avoir extrait  les données de l'API avec le package ` Requests `, on les range dans des tableaux.
* Comme on ne peut pas trop gérer l'esthétique sur python, il a fallu créer une chaine de caractéres `HTML` dans lequel on insère nos éléments des tableaux avec par exemple `{tableau_vent[0]}` et nos images avec `< src = chemin/image.svg />`. 
* En utilisant un fichier `CSS`, il a été possible de modifier les aspects graphiques de mon tableau affichant la météo.
* Les données sur la vitesse du vent n'étant pas celles qu'on voulait, il a fallu les traiter pour en obtenir la moyenne.
* Enfin pour ce qui est des modifications de couleurs en fonction des valeurs de l'API, il a fallu créer des fonctions appropriées qui agissent sur les entiers des codages couleurs en RGBA.
* Le déploiement du site se fait à l'aide de github pages et s'actualise avec le programme `CRON` dans un fichier `.github/workflows/publish.yml`.
  
### Base de données

Pour cela j'utiliserai les données de prévision météo du site [open-meteo.com](open-meteo.com) que j'ai calibré à l'aide de la latitude et de la longitude de Montpellier.

* Pour la page principale de mon site, j'utilise les données dites "daily" du weathercode, de la température minimale et maximale et les données "hourly" de température, précipitation et de vitesse de vent.
* Pour la page donnant la météo dans la journée, j'utilise les données "hourly" du weathercode, de température, précipitation et de vitesse de vent.

### Appercu 

A chaques jours sont associés en fonction des données de l'API: 

| Elements | Exemple |
|:--    |:-:    |
| Un jour | Mardi |      
| Un pictogramme | <img src='iconsmeteo/wi-rain-wind.svg' width="50" height="50" /> |
| Une température maximale | 13.5°C |
| Une température minimale | 6.1°C |
| Une vitesse de vent moyenne | 9km/h |
| Une quantité de précipitations | 1.3mm |

- La base de données n'ayant que 4 jours de prévision, j'ai décidé d'afficher les données météo sur une plage de 7 jours en ajoutant donc 2 jours précédant la date actuelle. 
  
Des éléments visuels ont été ajoutés au code pour rendre le tableau plus attrayant. \
Il est également possible de naviguer entre la page de météo à la semaine et de météo detaillée du jour en utilisant les lies hypertext en bleu dans les tableaux ou bien simplement avec le menu du haut de la page.

### Icones météo

Pour réaliser ce projet, j'ai utilisé des icônes météo sous format `svg` provenant du git suivant: [github.com/erikflowers/weather-icons](https://github.com/erikflowers/weather-icons)


