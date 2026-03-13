---
title: "Obsidian - Markdown : les liens externes et internes"
date: 2024-06-08T08:00:00+02:00
draft: false
tags: ["Obsidian"]
categories: ["Obsidian"]
series: ["Obsidian"]
description: "Maîtrisez les liens externes et internes en Markdown dans Obsidian pour connecter vos notes et ressources web."
cover:
  image: "images/Pasted_image_20230722204313.jpg"
  alt: "Markdown - Liens externes dans Obsidian"
---

Dans l’[article précédent](/posts/obsidian-markdown-premiere-partie), nous avons commencé à découvrir le <a target="_blank" rel="noopener noreferrer" href="https://fr.wikipedia.org/wiki/Markdown"> **Markdown**</a> avec le formatage des notes dans <a target="_blank" rel="noopener noreferrer" href="https://obsidian.md/"> **Obsidian**</a>.

Dans cet article, nous allons regarder comment réaliser des liens externes et internes en <a target="_blank" rel="noopener noreferrer" href="https://fr.wikipedia.org/wiki/Markdown"> **Markdown**</a>.

## Liens externes

### Lien externe vers une page web

Pour faire un lien vers une page web, indiquez entre crochet le texte qui sera visible puis entre parenthèse l’URL : 
```md 
[Obsidian](http://obsidian.md)
```

Ce que vous devez écrire :
{{< img src="/images/Pasted_image_20230722204313.jpg" alt="Lien externe - Edition" class="center" >}}

Ce que vous obtiendrez : 
{{< img src="/images/Pasted_image_20230722204318.jpg" alt="Lien externe - Visualisation" class="center" >}}


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
{{< img src="/images/Pasted_image_20230722204334.jpg" alt="Image - Edition" class="center" >}}

Ce que vous devez obtiendrez :
{{< img src="/images/Pasted_image_20230722204338.jpg" alt="Image - Visualisation" class="center" >}}


## Liens internes

Pour les exemples qui suivent nous allons créer une nouvelle note intitulée **Ma deuxième note** :

{{< img src="/images/Pasted_image_20230722204348.jpg" alt="Lien interne - Edition" class="center" >}}


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
{{< img src="/images/Pasted_image_20230722204402.jpg" alt="Lien vers une note - Edition" class="center" >}}

Ce que vous obtiendrez :
{{< img src="/images/Pasted_image_20230722204411.jpg" alt="Lien vers une note - Visualisation" class="center" >}}

### Lien vers le titre d’une note

Vous pouvez faire un lien vers l’un des titres contenus dans votre note, pour cela reprenez la syntaxe d’un lien vers une note et, après le nom de la note ajoutez un dièse # et choisissez le titre que vous souhaitez lier : 
```md
[[Ma deuxième note#Ceci est un titre]]
```

Obsidian vous propose le titre que vous souhaitez lier : 
{{< img src="/images/Pasted_image_20230722204431.jpg" alt="Lien vers un titre - Proposition" class="center" >}}

Le résultat en mode Edition :
{{< img src="/images/Pasted_image_20230722204436.jpg" alt="Lien vers un titre - Edition" class="center" >}}

Le résultat en mode Visualisation :
{{< img src="/images/Pasted_image_20230722204441.jpg" alt="Lien vers un titre - Visualisation" class="center" >}}

### Lien vers le contenu d’une note

Vous pouvez également faire un lien vers le contenu d’une note, pour cela reprenez la syntaxe d’un lien vers une note et, après le nom de la note ajoutez un accent circonflexe ^ et choisissez le contenu que vous souhaitez lier : 
```md
[[Ma deuxième note^c095da]]
```
Obsidian vous propose le contenu que vous souhaitez lier : 
{{< img src="/images/Pasted_image_20230722204450.jpg" alt="Lien vers une contenu - Proposition" class="center" >}}

Le résultat en mode Edition :
{{< img src="/images/Pasted_image_20230722204455.jpg" alt="Lien vers une contenu - Edition" class="center" >}}

Le résultat en mode Visualisation :
{{< img src="/images/Pasted_image_20230722204459.jpg" alt="Lien vers une contenu - Visualisation" class="center" >}}


