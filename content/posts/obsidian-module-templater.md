---
title: "Obsidian - Module Templater"
date: 2024-06-13T10:56:53+02:00
draft: false
---
Dans l’[article précédent](/posts/obsidian-module-periodic-notes), nous avons installé le module complémentaire [Periodic Notes](/posts/obsidian-module-periodic-notes) et nous l'avons configuré.

Nous allons maintenant installé le module **Templater** de **SilentVoid** et dans les prochains posts nous paramétrons les différents modèles de notes (daily, weekly, monthly...).

## Templater
Une fois le module complémentaire installé, quelques parmaètres à mettre à jour.
![Module Calendar](/images/Pasted_image_20240616110148.png#center)



**Templater folder location :** 00_INBOX/00_TEMPLATES
![Module Calendar](/images/Pasted_image_20240616110616.png#center)

**Trigger Templater on new file creation :** true
**Show icon in sidebar :** false
![Module Calendar](/images/Pasted_image_20240616110656.png#center)


Maintenant je vais vous montrer comment l'utiliser dans les différents modèles de notes que nous avons créés pour notre journal.

## Daily

### Propriétés

Premièrement, nous allons, tout en haut de la note Daily Note Template, écrire trois tirets ```---``` afin de faire apparaître les Propriétés.

Les Propriétés sont des méta-données liées à la note. Nous pouvons y inscrire des informations sur la note et nous verrons par la suite comment nous pourrons les exploiter.

Voici les propriétés que possèdent mon modèle de note pour mes notes quotidiennes :

**type : ** *daily*, il indique le type de note qui vont être produites via ce modèle.

**day : ** *<% tp.file.creation_date("YYYY-MM-DD") %>*, nous utilisons Templater pour obtenir la date de création de la note.

**week : ** *<% tp.file.creation_date("YYYY-WW") %>*, nous utilisons Templater pour obtenir la semaine de création de la note.

**month : ** *<% tp.file.creation_date("YYYY-MM") %>*, nous utilisons Templater pour obtenir le mois de création de la note.

**quarter : ** *<% tp.file.creation_date("YYYY-0Q") %>*, nous utilisons Templater pour obtenir le trimestre de création de la note.

**year : ** *<% tp.file.creation_date("YYYY") %>*, nous utilisons Templater pour obtenir l'année de création de la note.

Ensuite, en m'inspirant du livre <a target="_blank" href="https://amzn.to/4c1uESn">Miracle Mornin de Hal Elrod</a>, j'ajoute les six habitudes qu'il propose baptisés les SAVERS : 

**silence : ** *0* - prendre un temps en silence, pour ma part, de la méditation

**affirmation : ** *0* - se répéter des affirmations positives afin de booster sa confiance en soi

**visualisation : ** *0* - visualiser les objectifs que vous souhaitez atteindre

**exercice : ** *0* - réaliser une activité physique

**read : ** *0* - s'accorder du temps pour lire

**scribe : ** *0* - écrire ce que vous souhaitez, l'important étant de prendre l'habitude d'écrire

J'initialise chaque action à 0, et lorsque je l'aurai réaliser, je la passerai à 1.




