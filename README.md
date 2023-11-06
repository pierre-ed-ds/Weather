# Météo Montpellier
## Objectif

Le but de ce site est d'afficher les prévisions météo de montpellier sur un intervalle de quatre jours.

## Site web Quarto

Il est possible de consulter mon site sous l'adresse suivante: [pierre-ed-ds.github.io/Weather](https://pierre-ed-ds.github.io/Weather/). \
Ce site à été deployé avec github pages et s'actualise automatiquement à 1h00, 8h00, 13h00 et 18h00. 

## Base de données

Pour cela j'utiliserai les données de prévision météo du site [open-meteo.com](open-meteo.com) que j'ai calibré à l'aide de la lattitude et de la longitude de Montpellier.

* Pour la page principale de mon site, j'utilise les données dites "daily" du weathercode et les données "hourly" de température, précipitation et de vitesse de vent.
* Pour la page donnant la météo dans la journée, j'utilise les données "hourly" du weathercode, de température, précipitation et de vitesse de vent

## Appercu 

A chaques jours sont associés en fonction des données de l'API: 

| Elements | Exemple |
|:--    |:-:    |
| Un jour | Mardi |      
| Un pictogramme | <img src='iconsmeteo/wi-rain-wind.svg' width="50" height="50" /> |
| Une température maximale | 13.5°C |
| Une température minimale | 6.1°C |
| Une vitesse de vent moyenne | 9km/h |
| Une quantité de précipitations | 1.3mm |

La base de donnée n'ayant que 4 jours de prevision, j'ai decidé d'afficher les données météo sur une plage de 7 jours en ajoutant donc 2 jours précédant la date actuelle. \
Des éléments visuels ont été ajoutés au code pour rendre le tableau plus attrayant. \
Il est également possible de naviguer entre la page de météo à la semaine et de météo detaillé du jour en utilisant le <span style="color: rgb(85, 215, 195);"> < </span>, le <span style="color: rgb(85, 215, 195);"> > </span>, ou bien simplement avec le menu du haut de la page.

## Icones météo

Pour réaliser ce projet, j'ai utilisé des icones météo sous format svg provenant du git suivant: [github.com/erikflowers/weather-icons](https://github.com/erikflowers/weather-icons)