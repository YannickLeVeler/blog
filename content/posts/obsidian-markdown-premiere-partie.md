---
title: "Obsidian - Markdown : la mise en forme"
date: 2024-06-07T08:00:00+02:00
draft: false
tags: ["Obsidian"]
---
Grâce à l’[article précédent](/posts/obsidian-synchronisation-via-dropbox), nous avons maintenant un coffre **Formation** synchronisé sur deux ordinateurs Windows et un téléphone.

Pour l’instant ce coffre contient un dossier **Notre premier dossier** et une note, **Notre première note.**

Comme précisé dans un précédent article, le format des notes dans <a target="_blank" href="https://obsidian.md/"> **Obsidian**</a> est le <a target="_blank" href="https://fr.wikipedia.org/wiki/Markdown"> **Markdown**</a>.

Je vous propose dans cet article de découvrir les principales basiles pour formater vos notes. Je mets de coté pour un prochain article toutes les balises qui permettent de faire des liens.

## Format Markdown

Je vous propose de vous montrer le format brut à gauche avec les balises à gauche et à droite le rendu dans <a target="_blank" href="https://obsidian.md/"> **Obsidian**</a>.

## Titres

Six niveaux de titres sont disponibles. Pour chaque niveau, ajoutez un dièse.  
Attention à bien respecter l’espace entre le dernier dièse et le titre, sinon vous créez un tag.

Ce que vous devez écrire en mode Edition : 
![Titre - Visualisation](/images/Pasted_image_20230722203923.jpg#center)

Ce que vous obtiendrez en mode Visualisation: 
![Titre - Visualisation](/images/Pasted_image_20230722203938.jpg#center)

## Formatage du texte

Deux étoiles ** ou deux tirets bas __ avant et après un texte pour le mettre en gras : 
```md
**Ce texte est en gras**, __Ce texte est aussi en gras__
```

Une étoile * ou un tiret bas _ avant et après un texte pour le mettre en italique : 
```md
*Ce texte est en italique*, _Ce texte est aussi en italique_
```

Trois étoiles *** ou trois tirets bas ___ avant et après un texte pour le mettre en gras et en italique : 
```md
***Gras et italique***, ___Gras et italique___
```

Deux signes égal == avant et après un texte pour le surligner : 
```md
==Ce texte est surligné==
```

Deux tildes ~~ avant et après un texte pour le barrer : 
```md
~~Ce texte est barré~~
```

Ce que vous devez écrire en mode Edition : 
![Formatage - Edition](/images/Pasted_image_20230722203954.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Formatage - Visualisation](/images/Pasted_image_20230722203958.jpg#center)

## Listes

Pour la liste numérotée, il suffit d’indiquer un chiffre puis un point : 
```md
1. Item 1  
```

Pour la liste non numérotée, il suffit d’indiquer une étoile : 
```md
* Item 1
```

Ce que vous devez écrire en mode Edition : 
![Liste - Edition](/images/Pasted_image_20230722204008.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Liste - Visualisation](/images/Pasted_image_20230722204013.jpg#center)

## Tâches

Pour afficher une tâche à réaliser, indiquez un tiret puis un crochet ouvert, un espace et un crochet fermé : 
```md
[ ] Tâche 1  
```

Pour afficher une tâche réalisée et la barrer, indiquez un tiret puis un crochet ouvert, la lettre x et un crochet fermé : 
```md
[x] Tâche 2  
```

Pour afficher une tâche réalisée sans la barrer, indiquez un tiret puis un crochet ouvert, un point d’interrogation et un crochet fermé : 
```md
[?] Tâche 3
```

Ce que vous devez écrire en mode Edition : 
![Tâche - Edition](/images/Pasted_image_20230722204025.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Tâche - Visualisation](/images/Pasted_image_20230722204029.jpg#center)

## Tableau

Pour les entêtes de colonne du tableau, séparez le nom des colonnes par une barre verticale | : 
```md
Titre 1 | Titre A
```

Vous devez séparer l’entête des colonnes du contenu du tableau avec à minima un tiret séparé par des barres verticales : 
```md
– | –  
```

Pour le contenu du tableau, séparez les différentes cellules par une barre verticale : 
```md
Contenu 1 | Contenu B
```

Ce que vous devez écrire en mode Edition : 
![Tableau - Edition](/images/Pasted_image_20230722204039.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Tableau - Visualisation](/images/Pasted_image_20230722204045.jpg#center)

## Bloc de code

Pour afficher un bloc de code, commencez par trois accents graves et indiquez le langage de programmation.  

Pour connaitre les langages supportés, utilisez le site suivant : [https://prismjs.com/#supported-languages](https://prismjs.com/#supported-languages).  

Ecrivez votre code et terminez par trois accents graves.

Ce que vous devez écrire en mode Edition : 
![Bloc de code - Edition](/images/Pasted_image_20230722204056.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Bloc de code - Visualisation](/images/Pasted_image_20230722204100.jpg#center)

## Code en ligne

Le texte présent entre accent grave dans un texte sera formaté comme du code.

Ce que vous devez écrire en mode Edition : 
![Code en ligne - Edition](/images/Pasted_image_20230722204109.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Code en ligne - Visualisation](/images/Pasted_image_20230722204114.jpg#center)

## Séparation horizontale

Pour faire une séparation horizontale dans votre note, vous pouvez utiliser trois étoiles ***, trois tirets bas ___ ou trois tirets —

Ce que vous devez écrire en mode Edition : 
![Séparation horizontale - Edition](/images/Pasted_image_20230722204128.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Séparation horizontale - Visualisation](/images/Pasted_image_20230722204132.jpg#center)

## Citation

Commencez votre ligne avec un signe supérieur > pour pouvoir afficher un bloc de citation : > Ceci est une citation

Pour indiquer l’auteur de la citation, allez à la ligne puis mettez un antislash et un tiret : \- YALE, 2023

Ce que vous devez écrire en mode Edition : 
![Citation - Edition](/images/Pasted_image_20230722204141.jpg#center)

Ce que vous obtiendrez en mode Visualisation : 
![Citation - Visualisation](/images/Pasted_image_20230722204145.jpg#center)

Dans notre [prochain post](/posts/obsidian-markdown-deuxieme-partie), nous verrons les différents liens possibles en <a target="_blank" href="https://fr.wikipedia.org/wiki/Markdown"> **Markdown**</a>.