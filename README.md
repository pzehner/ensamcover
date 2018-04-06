# Paquet `ensamcover`

Ce paquet permet de créer la couverture et la quatrième de couverture d'un manuscrit de thèse ENSAM ou d'un autre établissement ParisTech.
Il s'agit d'une version améliorée et encapsulée du modèle créé par [Dorian Depriester](http://blog.dorian-depriester.fr/latex/page-de-garde-pour-manuscrit-de-these) en 2014.

Le paquet s'utilise avec PDFLaTeX, XeLaTeX ou LuaLaTeX.

![Première de couverture](tree/master/sample/sample_front.jpg)
![Quatrième de couverture](tree/master/sample/sample_rear.jpg)

## Installation

On peut copier le dossier du paquet dans son dossier de travail et l'importer avec :

```latex
\usepackage{path/to/ensamcover/ensamcover}
```

On peut aussi copier le dossier dans `~/texmf/tex/latex/`, actualiser l'index avec `texhash`, puis importer le paquet avec :

```latex
\usepackage{ensamcover}
```

## Utilisation

Le paquet défini un certain nombre de commandes pour peupler la page de couverture et la quatrième de couverture.
Les différentes commandes peuvent être définies directement dans le préambule du document ou dans un fichier `tex` séparé qu'il faut alors charger :

```latex
\loadcoverdata{fichier}
```

Pour créer la première page, il suffit d'appeler la commande :

```latex
\makefrontpage
```

Et pour la quatrième de couverture :

```latex
\makerearpage
```

### Couverture

```latex
\version{note de version}
```

Permet de spécifier une note de version sur la première page, par exemple « Mémoire provisoire. »
La note est affichée en rouge.

```latex
\doctorate{intitulé du doctorat}
```

Spécifie l'intitulé du doctorat, par exemple « Doctorat ParisTech. »

```latex
\doctorateschool{école doctorale}
```

Spécifie l'école doctorale avec son numéro, par exemple « École doctorale numéro 432 : Sciences des Métiers de l'Ingénieur. »
Le numéro doit pouvoir se trouver sur le site de l'école doctorale.

```latex
\institute{nom de l'école}
```

Spécifie l'établissement de l'école doctorale, par exemple « École Nationale Supérieure d'Arts et Métiers. »

```latex
\institutelogo{logo}
```

Si l'établissement est différent de l'ENSAM, permet de spécifier un autre fichier de logo.

```latex
\institutecolor{modèle}{spécification}
```

Si l'établissement est différent de l'ENSAM, permet de spécifier la couleur du titre et du bandeau en bas à droite.
Les arguments `modèle` et `spécification` sont similaires à ceux de la commande `\definecolor`.

```latex
\speciality{spécialité}
```

Spécifie la spécialité du doctorat.

```latex
\author{Prénom Nom}
```

Spécifie le nom du doctorant.

```latex
\title{Titre de la thèse \\ avec des effets de renvoi de ligne}
```

Spécifie le titre de la thèse sur la première page.

```latex
\thesisid{numéro de la thèse}
```

Numéro de la thèse donné après la soutenance, par exemple « 2018-ENAM-0001. »

```latex
\director{Directeur 1}
\director[p]{Directeur 1, Directeur 2}
```

Liste du ou des directeur(s) de thèse. 
Ajouter `p` pour spécifier qu'il y en a plusieurs.

```latex
\supervizor{Encadrant 1}
\supervizor[p]{Encadrant 1, Encadrant 2}
```

Liste du ou des encadrant(s) de thèse. 
Ajouter `p` pour spécifier qu'il y en a plusieurs.

```latex
\date{date de soutenance}
```

Date de la soutenance.

```latex
\jury{%
  \jurymember{Nom}{Titre, établissement}{Président}
  \jurymember{Nom}{Titre, établissement}{Rapporteur}
  \jurymember{Nom}{Titre, établissement}{Examinateur}
}
```

Composition du jury.
Utiliser la commande `jurymember` pour ajouter un membre au jury.
Pour le mémoire provisoire, on peut trier les noms par ordre alphabétique.
Pour la version finale, il faut les trier par rôle (président, rapporteurs puis examinateurs).

```latex
\adresse{Établissement}{Adresse}
```

Spécifie l'adresse de l'établissement.

### Quatrième de couverture

La quatrième de couverture est réservée aux résumés.

#### Résumé en français

```latex
\titlefr{Titre en français sans effet de renvoi de ligne}
```

Spécifie le titre.

```latex
\abstractfr{résumé proprement dit en français}
```

Le texte du résumé, il doit ne former qu'un seul paragraphe et ne pas dépasser 4000 caractères.

```latex
\keywordsfr{liste des mots clés en français}
```

Les mots clés peuvent être séparés par n'importe quel caractère.

#### Résumé en anglais

```latex
\titleen{Titre en anglais sans effet de renvoi de ligne}
```

Spécifie le titre.

```latex
\abstracten{résumé proprement dit en anglais}
```

Le texte du résumé, il doit ne former qu'un seul paragraphe et ne pas dépasser 4000 caractères.

```latex
\keywordsen{liste des mots clés en anglais}
```

Les mots clés peuvent être séparés par n'importe quel caractère.

## Dossier d'exemple

Le dossier `sample` contient un exemple complet.
