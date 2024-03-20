# Création de visites virtuelles et contenus pédagogiques en VR libres et gratuits

*Version 1*

> Auteurs:
> - **Maxime Renauld**, élève en TPRO SN RISC au lycée Louis de Cormontaigne, Metz
> - **Solenne Mvutu Mbeya**,  élève en TPRO SN RISC au lycée Louis de Cormontaigne, Metz
> - **Yanis Maafa**,  élève en TPRO SN SSIHT au lycée Louis de Cormontaigne, Metz
> - **Matthieu Farcot**, encadrement et validation, lycée Louis de Cormontaigne, Metz

## Objectif du document:
Expliquer comment créer et mettre en ligne des visites virtuelles incluant des éléments pédagogiques diversifiés. La technologie utilisée doit être entièrement gratuite et sous licence libre - y inclut l'hebergement. La technologie doit permettre une navoigation compatible avec les spécificités de multiples appareils, y inclut la navigation en VR 

Ce document doit inclure toutes les étapes de la réalisation, des prises de vue à l'édition du code en passant par l'hébergement. Le tout doit être écrit de la manière la plus simple et didactique possible, en procédant étape par étape.

La cible du document est le grand public *sans connaissances techniques préalables*.

## Introduction
Bienvenue sur notre page dédiée à la réalisation de panoramas 360° pour l’éducation en utilisant les bibliothèques A-Frame.

La réalité virtuelle a le potentiel de transformer l’éducation, en offrant des expériences d’apprentissage immersives et interactives. Les panoramas 360°, en particulier, peuvent permettre aux lycéens et étudiants de découvrir de nouveaux environnements et concepts d’une manière visuellement riche et engageante.

A-Frame, une bibliothèque JavaScript pour la création d’expériences de réalité virtuelle, rend cette technologie accessible à tous, même à ceux qui n’ont pas de connaissances approfondies en programmation. Avec A-Frame, vous pouvez consulter des panoramas 360° interactifs et immersifs directement dans votre navigateur web, ce qui est idéal pour une utilisation en classe ou à distance.

Sur cette page, nous vous guiderons à travers les étapes de la création de votre propre panorama 360° en utilisant A-Frame, spécifiquement adapté à un contexte éducatif. Nous commencerons par les bases, comme la configuration de votre environnement de développement et la prise de photos panoramiques, puis nous vous montrerons comment utiliser A-Frame pour assembler ces photos en une expérience de réalité virtuelle interactive.

Que vous soyez un enseignant cherchant à intégrer la réalité virtuelle dans votre salle de classe, un développeur web cherchant à créer des ressources éducatives interactives, ou simplement quelqu’un qui est curieux de la technologie de panorama 360°, nous espérons que vous trouverez cette page informative et utile. Bonne création !

# [Partie 1] - Matériel préparatoire et prises de vues

## En amont : La plannification

La plannification, définissant l'objet de la visite et le contenu qui devra s'afficher, est essentielle en amont de toute production. Ceci est plus simple à dire qu'à faire, mais il est essentiel de définir l'objectif de la visite et d'avoir une idée claire de *ce qui doit être montré*.

Dans notre cadre, nous allons réaliser une viste virtuelle simple du terrain de sport de lycée Louis de Cormontaigne à Metz, se basant sur deux panoramas à 360°. Cette visite devra inclure des informations textuelles, des images, des vidéos, et des objets en 3 dimensions qui s'insèrent naturellement dans un panorama en 360°. Pour simplifier l'exemple, nous allons lier deux panoramas 360° entre eux pour permettre de simuler une ballade. Suivant la logique de navigation entre panoramas, l'orientation de l'utilisateur dans un panorama va avoir un impact: il est plus naturel quand on se déplace d'un point A à un point B que la vue lors de l'arrivée au point B suive une ligne droite issue du point A, afin de faire comprendre l'idée du mouvement. De même, l'ensemble des panoramas seront enrichis avec du contenu pédagogique sous diverses formes. Ce contenu doit s'afficher *à sa place* dans le panorama (par exemple le texte qui donne des information sur un batiment doit flotter uniquement au dessus de ce batiment).

Ceci explique l'importance d'une reflexion en amont, afin d'être sûr d'avoir toutes les images requises. Prendre une prise de vue manquante dans un deuxième temps risque expose l'opération à des changement brutaux de conditions de navigation (lumière ou météo différente par exemple) qui vont nuire à l'immersion.

## Matériel nécéssaire

- Une caméra 360° (nous utiliserons une caméra Insta 360 pour cet exemple).
- Un pied pour appareil photo (afin d'avoir une hauteur de prise de vue fixe entre les différents panoramas)
- Un ordinateur, avec les logiciels suivants
  - Un environnement de développement (ici VS Codium)
  - Un logiciel d'édition et de retouche d'image (ici GIMP)
  - Un compte GitHub (nous utiliserons cette plateforme pour l'hebergement des scènes, et nous nous assurerons que vous puissiez retrouver les fichiers issus de ce document)

### Prise des vues 360°

Il est utile de bien plannifier en amont de toutes prises de vues les endroits où seront réalisés les photos.
En exterieur, des outils comme google earth sont particulièrement utiles.

![plannification](<partie2/resources/image/plan.jpg>)

L'importation des images est le moment ideal pour mofier la résolution  modifier la resolution de l'image de 2880 pixel par 1440 pixel avec le logiciel de la caméra puis j'ai flouté le visage pour par la suite les importer 

on va utiliser le code suivant pour importer l'image 360 sur le navigateur:
```
<!DOCTYPE html>
<html>
  <head>
    <script src="https://aframe.io/releases/1.5.0/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <a-sky src="./images/3601.jpg"></a-sky>
    </a-scene>
  </body>
</html>
```
*... et c'est tout!*

Nous créons donc un document html à la racine de notre compte Github intitullé index.html


## Création d’un compte GitHub :


Pour commencer à utiliser GitHub, vous devez créer un compte personnel gratuit sur GitHub.com.


Suivez les invites pour créer votre compte personnel Assurez-vous d’utiliser un mot de passe fort et unique.


Vérifiez votre adresse e-mail lors de l’inscription. Sans adresse e-mail vérifiée, certaines tâches de base sur GitHub, comme la création d’un référentiel, ne seront pas possibles.


### Création d’un dépôt pour votre site :


Vous pouvez créer un nouveau dépôt ou utiliser un dépôt existant pour votre site.


Pour créer un nouveau dépôt :
Cliquez sur le bouton “+” dans le coin supérieur droit de n’importe quelle page, puis sélectionnez “Nouveau référentiel”.


Choisissez un nom pour votre référentiel (par exemple, <votre-nom-d'utilisateur>.github.io).


Sélectionnez “Public” comme visibilité du dépôt.
Cochez l’option “Initialize this repository with a README” (Initialiser ce dépôt à l’aide d’un fichier LISEZMOI).


Cliquez sur “Créer le dépôt”.


### Création de votre site :


Accédez au dépôt de votre site sur GitHub.


Configurez une source de publication pour votre site. Vous pouvez choisir entre différentes options, comme une branche dédiée ou un workflow GitHub Actions personnalisé.


Créez le fichier d’entrée pour votre site (par exemple, un fichier HTML, Markdown, etc.).


Publiez votre site en poussant vos fichiers vers le dépôt sur GitHub.


Votre site sera accessible via l’URL https://<votre-nom-d'utilisateur>.github.io.


Remarque : Les sites GitHub Pages sont disponibles publiquement sur Internet, même si leur dépôt est privé. Assurez-vous de ne pas inclure de données sensibles dans votre dépôt avant la publication

## Explication du code

Ce code est un exemple simple d’une page Web qui utilise la bibliothèque JavaScript A-Frame pour afficher une image à 360 degrés. Voici une explication détaillée de chaque partie :

`<!DOCTYPE html>` : Cette déclaration doit être la première ligne du document. Elle informe le navigateur que le document est une page HTML.

`<html>` : C’est la racine de la page HTML.

`<head>` : Cette balise contient des métadonnées sur le document HTML, qui ne sont pas affichées sur la page Web elle-même. Ici, elle contient une balise <script>.

`<script src="https://aframe.io/releases/1.5.0/aframe.min.js"></script>` : Cette balise importe la bibliothèque A-Frame, qui est une bibliothèque JavaScript pour la création d’expériences de réalité virtuelle.

`<body>` : Cette balise contient le contenu principal de la page Web, qui est affiché dans le navigateur.

`<a-scene>` : C’est une balise spécifique à A-Frame qui crée une scène 3D où vous pouvez placer des objets.

`<a-sky src="./images/3601.jpg"></a-sky>` : Cette balise spécifique à A-Frame crée un ciel autour de la scène avec comme texture l’image spécifiée. Dans ce cas, l’image est "3601.jpg" qui se trouve dans le répertoire "images".


`<a-scene>` est l’élément principal qui contient tous les objets 3D de la scène scène A-Frame.


`<a-assets>` est utilisé pour précharger les ressources, comme l'image de panorama.


`<img id="panorama-image" src="chemin_vers_votre_image.jpg">` définit une image que vous utiliserez pour le panorama. Remplace "chemin_vers_votre_image.jpg" par le chemin vers ton image de panorama.

`<a-sky src="#panorama-image"></a-sky>` crée le panorama en utilisant l’image que vous avez définie. Il utilise l’ID de l’image comme source.

N’oublie pas de remplacer "chemin_vers_votre_image.jpg" par le chemin réel vers ton image de panorama. Attention: l’image doit être au format equirectangular pour qu’elle s’affiche correctement comme un panorama 360°.


En résumé, ce code crée une scène de réalité virtuelle avec un ciel texturé par une image à 360 degrés. Vous pouvez interagir avec cette scène en utilisant la souris pour regarder autour de vous.

[LIen du site](https://maximer37.github.io/VR-Markdown/)

<!-- <a href="https://maximer37.github.io/VR-Markdown/"> -->


![*Premier panorama*](<partie2/resources/image/panorama1.jpg>)



![*Deuxième panorama*](<partie2/resources/image/panorama2.jpg>)
