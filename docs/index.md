# Les Filtres d'effets

## What is it?

On peut en CSS appliquer des effets sur un élément HTML grâce à sa propriété CSS "filter" et sa version préfixée "-webkit-filter.Il n'existe pas de version préfixée -o-filter, -moz-filter. Il existe bien une version -ms-filter pour Internet Explorer, mais il utilise sa propre implémentation. Cela permet donc d'altérer le rendu d'une image sans devoir stocker des dizaines de versions photoshopper de celle-ci.

## Le filtre de floutage gaussien

Le filtre de floutage gaussien permet comme son nom l'indique de flouter l'élément HTML. L'intérêt est de ne pas avoir à stocker une image photoshopper en plus mais de modifier directement l'image et d'ajuster plus facilement le floutage. Pour l'appliquer il faut utiliser le code CSS suivant:

```CSS

filter:blur(3px);

```
3px correspond au nombre de pixels qui vont se mélanger pour former le floutage. 0px fait qu'il n'y a aucun floutage et l'unité px peut être remplacée par n'importe quelle unité sauf %.

## Le filtre en niveau de gris

Le filtre en niveau de gris converti en niveau de gris l'image sur lequel il est appliqué. La valeur du paramètre de la fonction grayscale définit l'intensité de cette conversion. En utilisant une valeur de 100%, elle sera complètement en niveaux de gris. 0% conservera l'image telle quelle. La valeur par défaut du paramètre est 0. Il suffit donc d'utiliser le css suivant pour l'image visée:


```CSS

filter:grayscale(30%);

```
## Le filtre sépia

## Le filtre de luminosité

## Le filtre d'ombre portée

## Le filtre de saturation

## Le filtre de contraste

## Le filtre d'opacité

## Le filtre d'inversion

## Le filtre de rotation de teintes

## Le filtre animé

# Les Blend mods
  
## Welcome to GitHub Pages
```

You can use the [editor on GitHub](https://github.com/Manuel83/sample/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Manuel83/sample/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
