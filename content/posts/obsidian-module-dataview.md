---
title: "Obsidian - Module Dataview"
date: 2024-06-15T08:00:00+02:00
draft: false
tags: ["Obsidian"]
---
Dans l’[article précédent](/posts/obsidian-daily-note-template), nous avons commencé le template de notre Daily Note. Cela nous a permis de présenter le concept de méta-donnée avec les Propriétés.

Avant d'aller plus loin sur ce template, nous allons installé le module <a target="_blank" href="https://github.com/blacksmithgu/obsidian-dataview"> **Dataview**</a> de **Michael Brenan** et présenter son fonctionnement.


## Qu'est ce que le module Dataview ?

<a target="_blank" href="https://github.com/blacksmithgu/obsidian-dataview"> **Dataview**</a> est un module communautaire pour **Obsidian** qui vous permet de faire des requêtes sur votre coffre-fort en vous basant sur les méta-données et les tags contenus dans vos notes.

## Installation et configuration

Nous allons donc installé le module et, pour le moment, nous n'allons pas changer les paramètres.

![Module Dataview](/images/Pasted_image_20240826131103.jpg#center)


## Utilisation

Pour écrire une requête dataview, nous allons écrire un bloc de codes en démarrant par trois accents grave suivis du mot clé <a target="_blank" href="https://github.com/blacksmithgu/obsidian-dataview"> **Dataview**</a>.

Ensuite, nous écrirons notre requête puis nous terminerons notre bloc de codes par trois accents graves.

Si vous possédez peu de notes dans votre coffre-fort, vous pouvez écrire ce premier exemple qui va afficher sous forme de liste les liens vers toutes les notes que vous possédez.

Exemple : 
![Exemple Dataview](/images/Pasted_image_20240830145311.jpg#center)


Résultat : 
![Résultat Dataview](/images/Pasted_image_20240830145341.jpg#center)


## Structure de la requête

Pour ceux qui sont familiers avec le SQL (Structured Query Language), <a target="_blank" href="https://github.com/blacksmithgu/obsidian-dataview"> **Dataview**</a> propose des similitudes.

Pour écrire une requête, vous devrez définir : 
- le format de sortie (l'équivalent du SELECT en SQL)
- la source (l'équivalent du FROM en SQL)
- les conditions d'affichage (l'équivalent du WHERE, SORT, GROUP BY, LIMIT...)

Avant d'aborder en détail chaque étape, je vais vous présenter les méta-datas implicites que l'on peut utiliser dans <a target="_blank" href="https://github.com/blacksmithgu/obsidian-dataview"> **Dataview**</a>. Ces éléments nous seront utiles pour le format de sortie et les conditions d'affichage.

### Champs implicites

<a target="_blank" href="https://github.com/blacksmithgu/obsidian-dataview"> **Dataview**</a> ajoute automatiquement une grande quantité de métadonnées à chaque page. Ces champs implicites sont accessibles via le mot clé : **file**.

| Champs | Type | Description |
|---|---|---|
| *file.name* | Texte | Nom de la note |
| *file.folder* | Texte | Arborescence du répertoire de la note |
| *file.path* | Texte | Arborescence de la note |
| *file.ext* | Texte | L'extension de la note |
| *file.link* | Lien | Lien vers la note |
| *file.size* | Nombre | Taille de la note |
| *file.ctime* | Date avec heure | Date de création de la note |
| *file.cday* | Date | Date de création de la note |
| *file.mtime* | Date avec heure | Date de dernière modification de la note |
| *file.mday* | Date | Date de dernière modification de la note |
| *file.tags* | List | Une liste unique des tags présents dans la note en arboresence |
| *file.etags* | Texte | Une liste unique des tags présents dans la note |
| *file.inlinks* | Texte | Liste des liens entrants de la note |
| *file.outlink* | Texte | Liste des liens sortants de la note |
| *file.aliases* | Texte | Liste des alias définis dans les propriétés de la note |
| *file.tasks* | Texte | Liste des tâches présents dans la note |
| *file.lists* | Texte | Une liste de tous les éléments lists de la note (y compris les tâches)|
| *file.frontmatter* | Texte | Les valeurs brutes des propriétés de la note sous le format Proprieté - Valeur |
| *file.day* | Texte | Date dans le nom du fichier |
| *file.starred* | Booléen | Pour savoir si la note est en Favoris |

Vous allez pouvoir utiliser ces champs implicites pour constituer vos requêtes. 
Regardons maintenant les formats de sortie.


### Le format de sortie

Il existe quatre formats de sortie disponibles dans **Dataview**.

#### TABLE
Le format de sortie sera un tableau dans lequel nous pourrons préciser les colonnes que nous souhaitons visualiser sachant que la première colonne sera toujours un lien vers la note affichée.

Pour indiquer les colonnes que nous souhaitons afficher, il suffit d'écrire après le mot clé **TABLE**, les propriétés qui nous intéressent.

Vous pouvez renommer chaque colonne de votre tableau en utilisant le mot clé `as`. 
Par exemple, `file.folder as dossier` va renommer la colonne *file.folder* de votre tableau en *dossier* et afficher pour chaque note le champs implicite *file.folder*.

Exemple : 
![Exemple Dataview](/images/Pasted_image_20240830213820.jpg#center)


Résultat : 
![Résultat Dataview](/images/Pasted_image_20240830213833.jpg#center)


Dans cet exemple, on affiche donc une table contenant :
- un lien vers la note,
- le contenu de la propriété *type* de la note (que nous avons paramétré sur notre template pour la note quotidienne dans l'[article précédent](/posts/obsidian-daily-note-template))
- le dossier de la note en utilisant le champ *implicite file.folder*

Si vous ne souhaitez pas afficher le lien de la note, présente par défaut, vous pouvez utiliser les mots clés WITHOUT ID.

Exemple : 
![Exemple Dataview](/images/Pasted_image_20240902130042.jpg#center)


Résultat : 
![Résultat Dataview](/images/Pasted_image_20240902130116.jpg#center)


#### LIST
Le format de sortie sera une liste de liens vers vos notes.

Exemple : 
![Exemple Dataview](/images/Pasted_image_20240830145311.jpg#center)


Résultat : 
![Résultat Dataview](/images/Pasted_image_20240830145341.jpg#center)


Si vous le souhaitez, vous pouvez ajouter une information (et une seule) à afficher.

Exemple : 
![Exemple Dataview](/images/Pasted_image_20240901202543.jpg#center)


Résultat : 
![Résultat Dataview](/images/Pasted_image_20240901202612.jpg#center)


Et vous pouvez détourner cette contrainte, en affichant un champs calculé qui pourrait concaténer les champs dont vous avez besoin. 

Exemple : 
![Exemple Dataview](/images/Pasted_image_20240901203356.jpg#center)


Résultat : 
![Résultat Dataview](/images/Pasted_image_20240901203415.jpg#center)


De la même manière que pour la TABLE, vous pouvez utiliser les mots clés WITHOUT ID afin de ne pas afficher les liens des notes.


#### TASK
Le format de sortie sera une liste interactive des tâches sélectionnées dans votre coffre-fort. En effet, vous pourrez mettre à jour les tâches affichées dans dataview, elles se mettront automatiquement à jour dans la note d'origine.

Pour vous montrer son fonctionnement, je vais créer une note à la racine du coffre-fort et créer deux tâches à l'intérieur : 
![Exemple Dataview](/images/Pasted_image_20240902130947.jpg#center)


Dans notre requête dataview, nous allons indiquer le mot clé TASK :
![Exemple Dataview](/images/Pasted_image_20240902131050.jpg#center) 


On obtient comme résultat les tâches présentes dans l'ensemble du coffre-fort, dans notre cas, les deux tâches contenues dans la note Exemple : 
![Exemple Dataview](/images/Pasted_image_20240902131202.jpg#center) 


Si on coche la tâche dans le résultat de la requête dataview, la tâche présente dans la note d'origine sera mise à jour automatiquement : 
![Exemple Dataview](/images/Pasted_image_20240902131321.jpg#center) 


Et, en bonus, lorsque vous cliquez sur l'intitulé de la tâche, vous arrivez automatiquement sur la tâche dans la note d'origine.


#### CALENDAR
Le dernier format de sortie va vous permettre un affichage sous la format d'un calendrier mensuel où chaque résultat est représenté par un point sur la date concernée.

Par exemple, nous allons afficher sur un calendrier la date de création de chaque note.

Exemple : 
![Exemple Dataview](/images/Pasted_image_20240909213047.jpg#center)


Résultat : 
![Exemple Dataview](/images/Pasted_image_20240909213104.jpg#center)

Et, évidemment, vous pouvez cliquer sur une date pour ouvrir la note concernée.

Maintenant que nous avons vu l'ensemble des formats de sortie, nous verrons dans le prochain article la gestion des sources et les conditions d'affichage.