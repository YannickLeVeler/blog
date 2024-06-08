---
title: "Obsidian - Markdown : les liens externes et internes"
date: 2024-06-08T08:00:00+02:00
draft: true
---

Dans l’[article précédent](/posts/obsidian-markdown-premiere-partie), nous avons commencé à découvrir le <a target="_blank" href="https://fr.wikipedia.org/wiki/Markdown"> **Markdown**</a> avec le formatage des notes dans <a target="_blank" href="https://obsidian.md/"> **Obsidian**</a>.

Dans cet article, nous allons regarder comment réaliser des liens externes et internes en <a target="_blank" href="https://fr.wikipedia.org/wiki/Markdown"> **Markdown**</a>.

## Liens externes

### Lien externe vers une page web

Pour faire un lien vers une page web, indiquez entre crochet le texte qui sera visible puis entre parenthèse l’URL : 
```md 
[Obsidian](http://obsidian.md)
```

Ce que vous devez écrire :
![Lien externe - Edition](/images/Pasted_image_20230722204313.jpg#center)

Ce que vous obtiendrez : 
![Lien externe - Visualisation](/images/Pasted_image_20230722204318.jpg#center)


### Lien externe vers une image

On va reprendre la même syntaxe que pour le lien externe, et simplement ajouter un point d’exclamation en début de ligne : 
```md 
![Image](https://obsidian.md/images/banner.jpg)
```

Si vous souhaitez changez la taille de l’image vous pouvez indiquer la largeur en pixel après le libellé, séparé par une barre verticale :  
```md
![Image|200](https://obsidian.md/images/banner.jpg)
```

Ce que vous devez écrire :
![Image - Edition](/images/Pasted_image_20230722204334.jpg#center)

Ce que vous devez obtiendrez :
![Image - Visualisation](/images/Pasted_image_20230722204338.jpg#center)


## Liens internes

Pour les exemples qui suivent nous allons créer une nouvelle note intitulée **Ma deuxième note** :

![Lien interne - Edition](/images/Pasted_image_20230722204348.jpg#center)


### Lien vers une note

Pour insérer un lien vers une note existante, vous devez indiquer le nom de la note entre double crochets : 
```md 
[[Ma deuxième note]]  
```

Si vous souhaitez afficher un alias, vous devez l’indiquer après le nom de la note, séparée par une barre verticale : 
```md 
[[Ma deuxième note|2eme note]]
```

Lorsque vous tapez les deux premiers crochets [[, Obsidian vous propose les notes disponibles.]]

Ce que vous devez écrire : 
![Lien vers une note - Edition](/images/Pasted_image_20230722204402.jpg#center)

Ce que vous obtiendrez :
![Lien vers une note - Visualisation](/images/Pasted_image_20230722204411.jpg#center)

### Lien vers le titre d’une note

Vous pouvez faire un lien vers l’un des titres contenus dans votre note, pour cela reprenez la syntaxe d’un lien vers une note et, après le nom de la note ajoutez un dièse # et choisissez le titre que vous souhaitez lier : 
```md
[[Ma deuxième note#Ceci est un titre]]
```

Obsidian vous propose le titre que vous souhaitez lier : 
![Lien vers un titre - Proposition](/images/Pasted_image_20230722204431.jpg#center)

Le résultat en mode Edition :
![Lien vers un titre - Edition](/images/Pasted_image_20230722204436.jpg#center)

Le résultat en mode Visualisation :
![Lien vers un titre - Visualisation](/images/Pasted_image_20230722204441.jpg#center)

### Lien vers le contenu d’une note

Vous pouvez également faire un lien vers le contenu d’une note, pour cela reprenez la syntaxe d’un lien vers une note et, après le nom de la note ajoutez un accent circonflexe ^ et choisissez le contenu que vous souhaitez lier : 
```md
[[Ma deuxième note^c095da]]
```
Obsidian vous propose le contenu que vous souhaitez lier : 
![Lien vers une contenu - Proposition](/images/Pasted_image_20230722204450.jpg#center)

Le résultat en mode Edition :
![Lien vers une contenu - Edition](/images/Pasted_image_20230722204455.jpg#center)

Le résultat en mode Visualisation :
![Lien vers une contenu - Visualisation](/images/Pasted_image_20230722204459.jpg#center)


