---
title: "Espanso"
date: 2025-02-22T08:00:00+02:00
draft: false
tags: ["Espanso"]
---

<a target="_blank" href="https://espanso.org/">Espanso</a> de <a target="_blank" href="https://federicoterzi.com/">Frederico Terzi</a> est un Text Expander, c'est à dire, un outil qui va vous permettre de configurer des raccourcis clavier afin d'insérer rapidement des phrases, des mots ou des blocs de texte.

<a target="_blank" href="https://espanso.org/">Espanso</a> est un outil gratuit, open-source, supporté par Windows, Linux et macOS et basé sur des fichiers plats au format <a target="_blank" href="https://fr.wikipedia.org/wiki/YAML">YAML</a>.

J'utilise cet outil au quotidien, et grâce à lui je gagne énormément de temps. 

Comme d'habitude, je vous propose dans cet article, de vous montrer comment je l'ai installé et configuré.

Let's go !

## Installation
Télécharger l'application via leur <a target="_blank" href="https://espanso.org/install/">site internet</a> en fonction de votre OS et installez le.

Une fois installée, l'icône d'<a target="_blank" href="https://espanso.org/">Espanso</a> apparaît en bas à droite de votre écran. 
![Créer un nouveau coffre](/images/Pasted_image_20250219095100.jpg)

Afin de configurer les raccourcis, nous avons de besoin de trouver où sont stockés les fichiers de configuration.

Pour ce faire, lancez la commande ```espanso path``` via l'invite de commandes. 
![Créer un nouveau coffre](/images/Pasted_image_20250219094530.jpg)

Si nous suivons le premier chemin indiqué, nous allons trouver deux répertoires **config** et **match**.
![Créer un nouveau coffre](/images/Pasted_image_20250219094725.jpg)



## Configuration

### Config

Le premier dossier **config**, contient un fichier *default.yml*. 

Ce fichier va vous permettre de configurer <a target="_blank" href="https://espanso.org/">espanso</a> notamment afin désactiver <a target="_blank" href="https://espanso.org/">espanso</a> quand vous utilisez certaines applications ou définir une touche pour activer ou désactiver <a target="_blank" href="https://espanso.org/">espanso</a>.

La seule modification que j'ai réalisée sur ce fichier consiste à activer l'auto restart afin qu'<a target="_blank" href="https://espanso.org/">espanso</a> se recharge dès qu'un fichier est modifié. 

```yaml
auto_restart: true
```

### Match

<a target="_blank" href="https://espanso.org/">Espanso</a> fonctionne de la manière suivante, il va détecter quand vous tapez un mot-clé que vous avez défini (*trigger*) et va le remplacer par un bloc de texte que vous avez paramétré (*replacement*).

![Créer un nouveau coffre](/images/Pasted_image_20250219095232.jpg)

Cette association entre un *trigger* et un *replacement* est nommé un *match*.

![Créer un nouveau coffre](/images/Pasted_image_20250219100248.jpg)

Ce sont ces différentes associations que nous allons spécifier dans différents fichiers <a target="_blank" href="https://fr.wikipedia.org/wiki/YAML">YAML</a> que nous allons stocker dans le répertoire **match**.

Par défaut, le dossier **match** contient un fichier *base.yml* avec plusieurs exemples d'utilisation : 

![Créer un nouveau coffre](/images/Pasted_image_20250222153358.jpg)

Vous pouvez créer autant de fichiers dans le dossier **match** que vous le souhaitez tant qu'ils respectent le même format que le fichier *base.yml*.

Maintenant, que nous avons identifié les fichiers à paramétrer, nous allons regarder les différentes possibilités de correspondances qui nous sont offertes. 

## Correspondances

Ci-après nous allons parcourir les correspondances que je suis amené à utiliser. 

Pour voir toutes les correspondances rendues possibles par <a target="_blank" href="https://espanso.org/">Espanso</a>, vous pouvez utiliser le lien suivant : https://espanso.org/docs/matches/basics/#
### Basic

La solution la plus simple consiste à indiquer un bloc de texte simple.

Avec la règle suivante, lorsque j'écrirais le raccourci suivant ```;me``` il sera automatiquement remplacé par le texte ```Yannick Le Véler```.

```yaml
matches:
  - trigger: ";me"
    replace: "Yannick Le Véler"
```

### HTML

Par moment, je vais avoir besoin d'une mise en former plus poussée. <a target="_blank" href="https://espanso.org/">Espanso</a> nous permet d'utiliser le format <a target="_blank" href="https://en.wikipedia.org/wiki/Markdown">Markdown</a> ou le format <a target="_blank" href="https://en.wikipedia.org/wiki/HTML">HTML</a>.

Pour l'exemple ci dessous, j'ai choisi l'option <a target="_blank" href="https://en.wikipedia.org/wiki/HTML">HTML</a>.

```yaml
  - trigger: ";sig"
    html:
                ---<br> 
                <b>Yannick Le Véler</b><br>
                Manager Data<br>
                Direction Digital Data<br>
                <b>Leroy Merlin France</b><br>
```

### Choix-multiple

Lorsque vous définissez deux résultats pour un même raccourci, <a target="_blank" href="https://espanso.org/">espanso</a> vous proposera une pop-up afin de choisir quel résultat vous voulez appliquer.

```yaml
  - trigger: ";thk"
    replace: "Merci,"
    
  - trigger: ";thk"
    replace: "Merci d'avance,"
```

La pop-up en question : 
![Créer un nouveau coffre](/images/Pasted_image_20250219101705.jpg)

### Dynamique

Le prochain exemple va utiliser une variable et une extension et va nous permettre d'obtenir la date du jour grâce au raccourci ```;date```.

```yaml
  - trigger: ";date"
    replace: "{{mydate}}"
    vars:
      - name: mydate
        type: date
        params:
          format: "%d/%m/%Y"
```

Cet exemple étant plus complexe, nous allons l'expliquer ligne à ligne.

```yaml
  - trigger: ";date"
```

Dans la première ligne, nous déclarons le déclencher ```;date``` que vous saisirez pour afficher la date.

```yaml
    replace: "{{mydate}}"
```

Dans la deuxième ligne, nous déclarons le texte de remplacement comme d'habitude, mais cette fois nous incluons la variable *mydate*, qui contiendra la sortie de l'extension utilisée ci-dessous.

```yaml
    vars:
      - name: mydate
        type: date
```

Dans les lignes suivantes, nous avons défini la variable *mydate* comme type *date*. Le type d'une variable définit l'extension qui sera exécutée pour calculer sa valeur. Dans ce cas, nous utilisons l'extension de date.

```yaml
        params:
          format: "%d/%m/%Y"
```

Dans les lignes restantes, nous avons déclaré les paramètres utilisés par l'extension, en l'occurrence le format de date.

Pour connaitre toutes les extensions disponibles dans <a target="_blank" href="https://espanso.org/">Espanso</a>, vous pouvez utiliser le lien suivant : https://espanso.org/docs/matches/extensions/#date-extension

### Formulaire

Le formulaire va permettre de définir des variables dans votre texte, et lorsque vous utiliserez le raccourci une pop-up apparaitra afin que vous puissiez remplir les espaces laissés par les variables.

J'utilise régulièrement les formulaires pour faire des réponses personnalisées par email. Le texte est identique pour chaque réponse, je change uniquement le prénom de mon interlocuteur.

L'extrait <a target="_blank" href="https://fr.wikipedia.org/wiki/YAML">YAML</a> correspondant au formulaire : 

```yaml
  - trigger: ";cvs"
    form: |
      Bonjour [[Prénom]],
      
      Merci pour la mise en visibilité de ce profil.
```

Pour ce formulaire, je vais avoir besoin d'appliquer des sauts de lignes. J'ajoute donc le symbole ```|``` après le mot clé ```form```.

La pop-up me permettant de remplacer la variable définie dans le formulaire : 
![Créer un nouveau coffre](/images/Pasted_image_20250219102231.jpg)


## Git

Souhaitant pouvoir utiliser ma configuration espanso sur plusieurs ordinateurs, je vous propose d'utiliser <a target="_blank" href="https://git-scm.com/">Git</a> et <a target="_blank" href="https://github.com/">Github</a>. 

Tout d'abord nous allons créer un dossier **C:\github\espanso** et déplacer les dossiers **config** & **match**.

Ensuite, nous allons supprimer le dossier **espanso** dans le répertoire d'origine : **C:\Users\yleve\AppData\Roaming\espanso**.

Après, nous allons créer un lien symbolique avec la commande suivante : ```mklink /J "C:\Users\yleve\AppData\Roaming\espanso" "C:\github\espanso"```.
![Créer un nouveau coffre](/images/Pasted_image_20250217113927.jpg)

Sur <a target="_blank" href="https://github.com/">Github</a>, nous allons créer un repository **espanso** en private.

Puis, avec **Git Bash**, dans le dossier **C:\github\espanso** nous allons écrire les commandes suivantes afin de stocker nos modifications sur <a target="_blank" href="https://github.com/">Github</a> : 
![Créer un nouveau coffre](/images/Pasted_image_20250222180208.jpg)

```git init``` afin créer un repository <a target="_blank" href="https://git-scm.com/">Git</a> pour ce répertoire. 

```git add .``` afin d'ajouter l'ensemble des fichiers du working directory au staging area. 

```git commit -m "init"``` afin d'enregistrer les fichiers dans le repository local

```git remote add origin https://github.com/YannickLeVeler/espanso.git``` afin d'indiquer le repository distant.

```git push``` afin de mettre à jour le repository sur <a target="_blank" href="https://github.com/">Github</a>


