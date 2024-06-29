---
title: "Obsidian Daily Note Template"
date: 2024-06-14T08:00:00+02:00
draft: true
---
## Daily

Dans l’[article précédent](/posts/obsidian-module-templater), nous avons installé le module complémentaire <a target="_blank" href="https://github.com/SilentVoid13/Templater"> **Templater**</a> et nous l'avons configuré.

Voyons son utilisation pour créer notre modèle de note pour nos notes quotidiennes.

## Daily Note Template

Premièrement, nous allons, tout en haut de la note Daily Note Template, écrire trois tirets ```---``` afin de faire apparaître les Propriétés.

Les Propriétés sont des méta-données liées à la note. Nous pouvons y inscrire des informations sur la note et nous verrons par la suite comment nous pourrons les exploiter.

Voici les propriétés que possèdent mon modèle de note pour mes notes quotidiennes :

### Propriétés de base 

Les propriétés suivantes sont sur toutes mes notes : 

- **type : ** *daily*, il indique le type de note qui vont être produites via ce modèle.

- **day : ** *[[<% tp.file.creation_date("YYYY-MM-DD") %> ))*, nous utilisons Templater pour obtenir un lien vers une note correspondant à la date de création de la note.

- **week : ** *<% tp.file.creation_date("YYYY-WW") %>*, nous utilisons Templater pour obtenir un lien vers une note correspondant à la semaine de création de la note.

- **month : ** *<% tp.file.creation_date("YYYY-MM") %>*, nous utilisons Templater pour obtenir un lien vers une note correspondant au mois de création de la note.

- **quarter : ** *<% tp.file.creation_date("YYYY-0Q") %>*, nous utilisons Templater pour obtenir un lien vers une note correspondant au trimestre de création de la note.

- **year : ** *<% tp.file.creation_date("YYYY") %>*, nous utilisons Templater pour obtenir un lien vers une note correspondant à l'année de création de la note.

### Propriétés spécifiques

Ensuite, on trouve des propriétés spécifiques à mon modèle de note quotidienne.

En m'inspirant du livre <a target="_blank" href="https://amzn.to/4c1uESn">Miracle Morning de Hal Elrod</a>, j'ajoute les six habitudes qu'il propose, baptisés les SAVERS : 

**silence : ** *0* - prendre un temps en silence, pour ma part, de la méditation

**affirmation : ** *0* - se répéter des affirmations positives afin de booster sa confiance en soi

**visualisation : ** *0* - visualiser les objectifs que vous souhaitez atteindre

**exercice : ** *0* - réaliser une activité physique

**read : ** *0* - s'accorder du temps pour lire

**scribe : ** *0* - écrire ce que vous souhaitez, l'important étant de prendre l'habitude d'écrire

J'initialise chaque action à 0, et lorsque je l'aurai réaliser, je la passerai à 1.

Pour ceux qui ne connaissent pas le livre <a target="_blank" href="https://amzn.to/4c1uESn">Miracle Morning de Hal Elrod</a>, nous en parlerons dans un prochain article. En attendant n'hésitez pas à le lire. 

Nous verrons dans un prochain article l'utilisation du module <a target="_blank" href="https://github.com/pyrochlore/obsidian-tracker"> **Tracker**</a> qui nous permettra de suivre nos réalisations.

### Contenu de la note

Maintenant que nous avons vu les propriétés, nous allons voir le contenu de la note en tant que tel.

#### Navigation

Le premier élément de ma note va me permettre de naviguer sur la note de la veille ou la future note.

Le code qui se base sur le module Templater est le suivant : 
```◀ [[<% tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD") %>]] | <% tp.file.title %> | [[<% tp.date.now("YYYY-MM-DD", +1, tp.file.title, "YYYY-MM-DD") %>]] ▶```

Si je souhaite accéder à ma note weekly, monthly, quaterly ou yearly, je peux y accéder via les propriétés de la note.


#### Citation du jour

Le deuxième élément est la citation du jour. Encore une fois nous nous baserons sur Templater pour l'obtenir : 
```<% tp.web.daily_quote() %>```



