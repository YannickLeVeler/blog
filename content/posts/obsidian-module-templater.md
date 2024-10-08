---
title: "Obsidian - Module Templater"
date: 2024-06-13T10:56:53+02:00
draft: false
tags: ["Obsidian"]
---
Dans l’[article précédent](/posts/obsidian-module-periodic-notes), nous avons installé le module complémentaire [Periodic Notes](/posts/obsidian-module-periodic-notes) et nous l'avons configuré.

Nous allons maintenant installé le module <a target="_blank" href="https://github.com/SilentVoid13/Templater"> **Templater**</a> de **SilentVoid** et dans les prochains posts nous paramétrons les différents modèles de notes (daily, weekly, monthly...).

## Qu'est ce que le module Templater
Templater est un module communautaire pour **Obsidian** qui vous permet de créer des modèles personnalisés pour vos notes. 

Il offre des fonctionnalités dynamiques, comme l'insertion de dates, la génération de contenu basé sur des conditions spécifiques, et l'exécution de scripts. 

Templater facilite la standardisation de vos notes, la saisie rapide de données répétitives, et l'amélioration de votre productivité globale.

## Installation et configuration

Une fois le module complémentaire installé, nous allons mettre quelques paramètres à jour.
![Module Calendar](/images/Pasted_image_20240616110148.jpg#center)



Tour d'abord l'endroit où se trouve nos templates : **Templater folder location :** 00_INBOX/00_TEMPLATES
![Module Calendar](/images/Pasted_image_20240616110616.jpg#center)


Ensuite, nous allons modifier deux options :
- La première a pour objectif d'activer le code Templater lors de la création d'une nouvelle note
- La deuxième de cacher l'icone Templater dans le menu à gauche d'**Obisdian**.
**Trigger Templater on new file creation :** true
**Show icon in sidebar :** false
![Module Calendar](/images/Pasted_image_20240616110656.jpg#center)


## Utilisation 

Templater va interpréter des commandes qui débutent par ```<%``` et qui se terminent par ```%>``` et qui contiennent une fonction.

Par exemple pour obtenir la date du jour, nous allons utiliser la fonction ```tp.date.now()``` en écrivant dans notre modèle de note la commande : ```<% tp.date.now() %>```.

Quand nous créerons une note à partir de ce modèle, <a target="_blank" href="https://github.com/SilentVoid13/Templater"> **Templater**</a> remplacera cette commande par la date du jour.

Il existe deux types de fonction :
- Les fonctions internes, qui sont natives au module Templater
- Les fonctions utilisateur, que vosu pourrez créer vous même en JavaScript

Pour le moment, nous ne nous interesserons qu'aux fonctions internes.


## Fonctions internes

Les fonctions sont réparties au sein de différents modules :
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/config-module.html"> **Config module**</a>
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/date-module.html"> **Date module**</a>
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/file-module.html"> **File module**</a>
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/frontmatter-module.html"> **Frontmatter module**</a>
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/hooks-module.html"> **Hooks module**</a>
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/obsidian-module.html"> **Obsidian module**</a>
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/system-module.html"> **System module**</a>
- <a target="_blank" href="https://silentvoid13.github.io/Templater/internal-functions/internal-modules/web-module.html"> **Web module**</a>

Celui que nous utiliserons le plus et le module de gestion des dates.

Et le plus simple et de vous montrer comment l'utiliser dans les différents modèles de notes que nous avons créés pour notre journal dans le prochain article.