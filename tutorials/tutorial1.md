---
title: Les bases du HTML / CSS
subtitle: Le HTML, responsable de la structure.
layout: tutorial
---

# HTML : un langage à balises pour structurer logiquement les documents


Le navigateur/browser est le logiciel que nous utilisons pour consulté les
documents disponibles sur le World Wide Web (on cite principalement Chrome,
Firefox et Internet Explorer/Edge).  Il sert principalement à visualiser via un
moteur de rendu des sites dont le contenu est obtenu par le protocole HTTP.  Le
but de ce TD est de comprendre comment se génère des pages du web "1.0" dites
aussi statiques.  Il s'agit de pages dont le contenu est déjà connu et stocké
sous forme de fichier HTML (par exemple, une base encyclopédique) et que
l'utilisateur va consulter.  Il peut s'agir plus généralement de votre site
internet à vous ou d'un petit site de fan qui n'a pas vocation à être modifier
tous les jours.


Pour afficher ce type de page internet, on utilise deux types de fichiers : HTML et CSS.

 * Le fichier contenant du HTML contient la structure de la page et son contenu ;  il précise au dela d'un texte brut ce qui relève d'un paragraphe, d'un titre à l'aide de balises (exemple `<p>`, `<title>`,...).
 * Le fichier contenant des CSS est responsable de a présenation de ces éléments (mettre ce paragraphe en rose, utiliser la fonte "San Serif" pour ce titre,... )

Le but de ce TD est de démystifier la façon dont est interprétée ces deux types de fichiers par le navigateur.
Pour cela nous allons réaliser un site dont le rendu correspond au fichier [target.png]({{site.baseurl}}/assets/target.png), en partant du fichier [index.txt]({{site.baseurl}}/index.txt), qui contient
le contenu quasiement "brut" du site à réaliser.
Nous allons tout d'abord nous consacrer à préciser la structure (le HTML donc) que l'on peut ajouter à notre contenu brut.
Nous verrons ensuite comment attendre le rendu proposer par [target.png]({{site.baseurl}}/assets/target.png) en réalisant un fichier CSS.


## Transformation d'un document texte en un document HTML

Pour ajouter de la structure à notre document, nous allons rajouter des balises.
Une balise commence par `<mabalise>`. La plupart des balises demandent d'ajouter aussi un pendant fermant : `</mabalise>`.


Exemple pour un paragraphe on écrit :

~~~
<p>Ceci est un paragraphe HTML puisqu'il est entouré des balises p </p>
~~~
{:.html}

Nous allons commencer par des balises un peu particulières, car elles sont de type "meta", elles sont plus là pour que le navigateur et le serveur s'entendent bien lors des transferts.
Par exemple nous préciserons l'encodage des fichiers, le doctype,...
Cela n'est pas très passionnant et nous resterons succinct sur cet aspect.

Récupérer le fichier [index.txt]({{site.baseurl}}/index.txt) (fichier de base de travail).

 1. Ouvrer ce fichier "index.txt" dans le navigateur.
 2. Sauvegarder ce fichier en local, et renommer le fichier en index.html, ouvrir le fichier dans un
   navigateur et observer le résultat.
 3. Observer la différence de rendu, 
   en première ligne du document. Observer le résultat.
 4. Utiliser le formulaire http://validator.w3.org/ pour faire analyser la
   conformité du document au standard html. Quel est le résultat ?
 5. Pour que le document soit valide et reconnu comme un document HTML 5 il est
   nécessaire d'ajouter la ligne `<!DOCTYPE html>` au tout début du
   fichier. Il faut aussi que le document soit entourer de la balise HTML (tous le document) et BODY (seuelemnt autours du contenu de l'article, pas head) Réessayer de le valider.
 6. L'entête du document est définie grâce à l'ajout des balises `<head>` et
   `</head>` qui doivent contenir la balise `<meta>`. Réessayer de le valider. Le
   validateur indique que l'élément head doit obligatoirement avoir un titre.
 7. Insérer après la balise `<meta>` un titre "Le site non officiel de Chuck Norris" encadré par
   les balises `<title>` et `</title>`. Observer le résultat et envoyer le fichier au
   validateur. Le titre défini est utilisé pour renommer l'onglet du navigateur.


Passer le document sous l'encodage utf-8 (que nous priviligierons désormais) en ajoutant la balise 
 `<meta charset="UTF-8" />`

A ce stade, le validateur indique que le fichier index.html est un document HTML 5 valide.

## Structure standard d'un document HTML

Nous allons utiliser notre navigateur pour "inspecter" notre page internet.
Pour cela nous conseillons Chrome ou Firefox. Appuyer sur la touche F12. Une partie de la page doit maintenant être utilisée
par l'outil de devellopement. Ce dernier doit présenter deux parties bien distinctes, une dédie au HTML et l'autre...aux CSS.
Ces outils sont fabuleux pour apprendre comment se construisent une page internet. Nous vous conseillons de jouer un peu avec pendant un quart d'heure.
Un clic droit avec la souris sur un élément du html d'une page suivi d'un "Examiner l'élément" vous permettra de jouer avec le HTML et les CSS.

1. Encadrer par les balises `<body>` et `</body>` toute la partie du document se trouvant
en dessous de `</head>`.
2. Insérer une balise `<html>` avant la balise `<head>` et une balise `</html>` après la
balise `</body>`.

Les balises HTML définissent une structure arborescente du document où :

* html est l'élément racine
* head et body sont les deux fils de l'élément html
* title et meta sont deux fils de l'élément head
* "Le site non officiel de Chuck Norris" est un fils de l'élément title.


## Les Commentaires en HTML
Il est possible de rajouter des commentaires dans le HTML. Cela n'est pas interpréter par le navigateur, et n'est donc pas visible par l'utilisateur. 
Il s'agit donc d'information laissées par des dévellopeurs pour des dévellopeurs. On les places entre les balises `<!--` et `-->` : 


~~~
<!--Cela est un commentaire dans un fichier HTML  -->
~~~
{:.html}

Il y a justement des commentaires dans le fichier index.html, comme autant de consignes afin de les remplacer par du HTML.
Nous expliciterons ces dernières dans les sections suivantes.

## Titres

Nous allons commencer par rajouter de la stucture à notre page.
Pour ce faire nous allons utiliser les balises `<h2>` à `<h3>` pour identifier les différentes sections (`<h1>` est utilisé pour le titre du document).
Si vous cherchez un bon exemple d'utilisation de balises `<h2>`, faites un clic droit sur le titre 'Titres' juste au dessus puis "inspecter l'élement".


<b>Exercice : </b>

Ajouter la balise `<h2>` à ces élements signifiées par les commentaires : `<!--section -->`. 

Les sous sections `<h3>` sont associés quant à eux aux commentaires : `<!--sous section -->`, ajouter les et recharger la page.


## Éléments de regroupement

### Paragraphes

Utiliser maintenant les balises `<p>` et `</p>` autour des paragraphes du document.
Les paragraphes vous sont signifiés par `<!--debut paragraphe -->` et `<!--fin paragraphe -->`. Si vous faites un clic droit inspecter l'élément sur ce paragraphe, 
vous verrez justement que ce texte est dans un paragraphe.


<a name="ul"></a>
### Listes

En HTML nous pouvvons faire des listes ordonnées ou pas :

~~~
<ul>
  <li>premier item</li>
  <li>deuxième item</li>
</ul>
<ol>
  <li>premier item</li>
  <li>deuxième item</li>
</ol>
~~~
{:.html}

Ce qui donne une fois interprété par le moteur de rendu du navigateur : 
<ul>
  <li>premier item</li>
  <li>deuxième item</li>
</ul>
<ol>
  <li>premier item</li>
  <li>deuxième item</li>
</ol>

<b>Exercice : </b>

1. Utiliser les balises `<ul>` et `<li>` pour structurer la liste à puces `<!--liste -->` dans index.html. (ne vous soucier pas encore des commentaires <!-- lien externe` pour l'instant )
2. Utiliser les balises `<ol>` et `<li>` pour structurer la liste numérotée `<!--liste numérotée -->` dans index.html.


## Image : un exemple d'élément embarqué


<b>Exercice : </b>
Télécharger l'image [chuck-jeune.jpg]({{site.baseurl}}/assets/chuck-jeune.jpg). Copier là dans un repertoire assets/img 
à partide votre fichier index.html.
Ajouter la via la balise `<img>` en début de section (voir le fichier [target.png]({{site.baseurl}}/assets/target.png))
en lieu et place du commentaire `<!--l'image de Chuck Young doit être positionnée ici  -->`.

~~~
<img src="./assets/img/chuck-jeune.jpg" alt="Chuck Jeune, la légende est en marche."/>
~~~
{:.html}

Faite de même avec l'image [beware.jpg]({{site.baseurl}}/assets/beware.jpg) : positionner là en lieu et place du commentaire `<!--l'image de Chuck Beware ici   -->`.


src et alt sont des attributs de l'élément img.

L'attribut alt permet d'ajouter un texte alternatif :

 * pour les navigateurs ne pouvant les afficher (navigateur textuel <a href="http://lynx.browser.org/">Lynx</a>)
 * pour les personnes ne pouvent pas bien les voir (aveugles ou déficits visuels légés). 

## Éléments sémantiques


<a name="semantic"></a>

### Liens

L'un des éléments les plus emblématique du HTML est sans doute la balise `<a>`.

Un lien est composé princpalement par une url cible et un libellé (qui sera visible par l'utilisateur et souligné en bleu):


~~~
<a href="http:://urlcible.com">le libellé</a>
~~~
{:.html}

 * Dans le cas d'un lien externe, il suffit de renseigner tel quel l'url de la cible : `<a href="http://lynx.browser.org/">Lynx</a>`


 * Dans le cas d'un lien interne, on va utiliser les ancres `#monancre`.
On aurra positionné quelque par dans le document  un lien cible :
`<a id="mon_ancre_en_debut_de_fichier"></a>`. Notre lien interne sera 
alors : `<a href="#mon_ancre_en_debut_de_fichier">Retour au haut de page</a>`


Chercher dans votre fichier index.html les commentaires `<!-- lien interne ...` et `<!-- lien externe ...`.
Et remplacer les par des balises `<a>`.

<a id="citation"></a>

### Table 

Les tables.


### Citation

<blockquote > 
Un biscuit ça n'a pas de 'spirit', c'est juste un biscuit. 
Mais avant c'était du lait, des oeufs. Et dans les oeufs, il 
y a la vie potentielle. 

<cite>Jean Claude Van Damme</cite>
</blockquote>

Les citations permettent d'identifier un court texte sur lequel on veut attirer l'attention.
C'est utiliser notamment pour montrer qu'on a du 'spirit'.

<b>Exercice : </b>


Utiliser la balise `blockquote` et `<cite>` pour mettre en avant la citation en tout début de document (rechercher `<!-- utilier blockquote ici  -->`).

### Emphase

La balise `<em>` permet de mettre en évidence des passages importants dans un
texte. Identifier les mots en gras dans le document .pdf et les marquer avec cette balise
dans le fichier HTML.

<b>Exercice : </b>

Mettre en emphase la phrase qui suit le commentaire : `<!-- mettre en emphase cette phrase -->`.

Nous en avons fini en ce qui concerne le contenu et la struture de notre site.

Une remarque peut être informulée de votre part : mais pourquoi le fait de rajouter <h1> a mon titre chnage effectivement l'apparence des titres ? cela n'est pas à la charge du CSS justement ?
Les navigateurs appliquent des css par défaut associés aux balises HTML (exemple : par convention les liens <a> sont en bleus et soulignés sans que l'on est rien à faire).
Cela évite d'avoir justement TOUT à refaire en CSS : des styles par défauts sont proposés.
Dans le TD suivant nous verrons comment améliorer l'aspect du site.

<!--
1. Passer le document sous l'encodage utf-8 (que nous priviligierons désormais).
2. Travaillez sur votre projet en définissant les structures HTML des pages de votre site web.
-->