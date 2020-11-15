---
layout: post
title:  DisasterTracker iOS
date:   2020-08-01 12:00:00 +0300
image:  disastertracker.png
tags:   iOS mobile app flutter
---

À partir de juillet c'était les vacances jusqu'au mois de septembre donc on avait seulement 2 mois de vacances. Sachant que je ne partirai pas dès le mois de juillet, je me suis dis «*Pourquoi pas créer une application mobile téléchargeable depuis l'un des différents stores, juste pour essayer!*»
C'est à partir de ce moment que l'idée m'est venu de créer **DisasterTracker**, une application mobile qui permet d'avoir des informations sur les catastrophes naturelles dans le monde.

# Déroulement

Concrètement voici la liste des choses à faire:

## Recherches de source de données

Après des heures à chercher des sources de données gratuites concernant les catastrophes naturelles, voici ceux qui ont été retenues:
<br>

![nasa-logo](https://eonet.sci.gsfc.nasa.gov/img/nasa-logo.svg)
***EONET Nasa API***
: Une API de la fameuse NASA qui traque les évènements naturels (séismes, volcan, feu de forêts...) grâce aux images satellites.
<br>

![usgs-logo](https://ny.water.usgs.gov/maps/habs/images/usgs-logo-black.png)
***USGS API***
: Une API de l'institut d'études géologique des États-Unis permettant de faire des requêtes pour avoir de l'information sur les séismes.
<br>

![gdacs-logo](https://brands.home-assistant.io/_/gdacs/logo@2x.png)
***GDACS RSS Flux***
: GDACS est un outil crée dans le but d'améliorer les alertes de catastrophes, cet outil étant le fruit de la coopération entre les Nations Unis (US), l'Union Européenne (EU) et d'autres sources.

## Développement de l'UI (interface utilisateur)

![flutter-logo](https://flutter.dev/assets/flutter-lockup-1caf6476beed76adec3c477586da54de6b552b2f42108ec5bc68dc63bae2df75.png)
<br>

Afin de créer l'application il fallait choisir un outil parmi tous ceux proposant la possibilité de créer une application mobile. Mon choix s'est porté sur **Flutter**, un outil développé par **Google** afin de créer plus facilement de belles applications. Cet outil a aussi été utilisé pour développer **[Georyx]({{ site.baseurl }}{% link _posts/2020-07-02-georyx.markdown %})**.
Pour l'UI, les idées pour les pages principales étaient:
- Une carte avec des icons pour représenter le type de catastrophe
- Une page comparable à un flux RSS sous la forme d'une liste verticale des catastrophes triées dans l'ordre chronologique (les plus récents en haut et les plus anciens en bas).
Afin d'implémenter tout cela **Google** dispose de nombreuses ressources pour la prise en main avec les *codelabs* pour **Flutter** et ses différentes APIs, par exemple **GoogleMapsAPIs** poru la carte.

## Liaison UI & données
![programming](https://cdn.pixabay.com/photo/2015/04/20/13/17/work-731198_1280.jpg)
<br>

Après une bonne prise en main de **Flutter** et son langage de programmation, ***Dart***, il a fallu crée des modèle pour les catastrophes naturels. ***Dart*** étant un langage permettant de créer l'*OPP* a.k.a *Oriented Object Programing* j'ai crée les classes et sous-classes suivantes:
- Disaster
  - 🌊 Flood
  - 🌋 Volcano
  - 🏜 Drought
  - ⛰ Earthquake
  - 🧊 Sea and Ice Lake
  - 🌪 Cyclone

Les constructeurs de chaque classe ont été adaptés en fonction de la source des données. Par exemple pour *EONET Nasa* et *USGS* les données se présentaient sous la forme de **JSON** tandis que pour *GDACS*, les données étaient sous la forme de page **XML**. Heuresement grâce à des plugins/packages **Dart** pour **JSON** et **XML**, le traitement des données n'a pas été trop difficile.

## Publication sur l'AppStore
![appstore-logo](https://developer.apple.com/news/images/og/app-store-og.png)
<br>

Le développement d'une version de utilisable de l'application étant faite, il était temps de la publier sur l'**AppStore**! Afin de publier l'application sur l'**AppStore**, **XCode** a été requis et un compte **Apple Developper** pour un abonnement de 100€ annuel.
Après quelque manipulations en suivant différents tutoriels sur **YouTube** l'application a réussi a être publiée sur l'**AppStore**. Cependant celà à demander du temps puisqu'il fallait qu'un développeur du côté d'Apple vérifie l'application, puis en cas de non conformité il fallait corriger les erreurs pointées par celui-ci jusqu'à obtenir son accord pour la publication.

# Résultat
![disastertracker-app]({{ site.baseurl }}/images/disastertracker-result.png)
<br>

Grâce à ce projet personnel, j'ai pu découvrir quelques étapes du développement d'une application mobile entre:
- Chercher une source de données
- Designer les pages
- Lier les données avec les éléments des pages
- Publier sur une plateforme
Cependant le travail étant conséquent, à moi seul ce fut difficile de tout faire et ça aurait pu être intéressant de faire ce projet en équipe.

> "Alone we can do so little, together we can do so much." – Helen Keller

***

# Sources:
https://eonet.sci.gsfc.nasa.gov/what-is-eonet <br>
https://earthquake.usgs.gov/fdsnws/event/1/ <br>
https://www.gdacs.org/

