# Les Filtres d'effets

## What is it?

On peut en CSS appliquer des effets sur un élément HTML grâce à sa propriété CSS "filter" et sa version préfixée "-webkit-filter.Il n'existe pas de version préfixée -o-filter, -moz-filter. Il existe bien une version -ms-filter pour Internet Explorer, mais il utilise sa propre implémentation. Cela permet donc d'altérer le rendu d'une image sans devoir stocker des dizaines de versions photoshopper de celle-ci. La propriété peut prendre la valeur "none" qui retire tous filtres sur le background de l'image ou une ou plusieurs des fonctions ci-dessous.

## Le filtre de floutage gaussien

Le filtre de floutage gaussien permet comme son nom l'indique de flouter l'élément HTML. Pour l'appliquer il faut utiliser le code CSS suivant:

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

La fonction CSS ``` sepia() ``` applique un filtre sépia sur l'image, lui donnant un aspect plus jaune/marron, voire vielli.
L'intensité du filtre est indiquée sous la forme d'un nombre entre 0 et 1 ou d'un pourcentage. Une valeur de 100% (ou 1) permttra d'obtenir une image complètement sépia tandis qu'une valeur de 0% (ou 0) laissera l'image inchangée.
Il faut utiliser le css suivant pour l'image visée:

```CSS

filter:sepia(0.65); /*Pareil que 65%*/
filter:sepia(100%); /*Image complètement sépia*/.

```

## Le filtre de luminosité

La fonction ``` brightness() ``` permet de modifier la luminosité d'une image. Un argument de 0% créera une image totalement noire et une valeur de 100% conservera l'image originale telle quelle. Il est possible d'utiliser des valeurs supérieures à 100% afin d'obtenir des images saturées en luminosité. La valeur par défaut pour l'argument est 1.

```CSS

filter: brightness(3%);

```

## Le filtre d'ombre portée

Une ombre portée est une version décalée, dans une couleur donnée, du canal alpha de l'image qui est affiché sous celle-ci. Le mot-clé inset n'est pas autorisée. Cette fonction est semblable à la propriété box-shadow plus répandue, seule différence : les navigateurs utilisent parfois l'accélération matérielle pour les filtres ce qui peut permettre d'obtenir de meilleurs performances. Pour mettre un filtre d'ombre portée, il faut utiliser la fonction ``` drop-shadow() ``` avec en paramètres obligatoires le décalage de l'ombre sur l'axe horizontal, le décalage sur l'axe vertical et le flou, le largeur et la couleur de l'ombre sont optionnels.

```CSS

filter: drop-shadow(16px 16px 10px black);

```

## Le filtre de saturation

L'image est saturée. La valeur de l'argument de la fonction ``` saturate() ``` indique la force de la saturation. Une valeur de 0% fera que l'image sera totalement désaturée et une valeur de 100% conservera l'image dans son état original. Les valeurs intermédiaires augmenteront progressivement la saturation jusqu'à la saturation d'origine. Il est possible d'utiliser des valeurs supérieures à 100% pour obtenir un effet de sursaturation. La valeur par défaut de l'argument est 1.

```CSS

filter: saturate(200%);

```

## Le filtre de contraste

La fonction ``` contrast() ``` permet d'ajuster le contraste d'une image. Une valeur de 0% créera une image entièrement grise. Une valeur de 100% conservera l'image d'origine. Il est possible d'utiliser des valeurs supérieures à 100% pour augmenter le contraste. La valeur par défaut de l'argument est 1.

```CSS

filter: contrast(200%);

```

## Le filtre d'opacité

La fonction ``` opacity() ``` permet de régler l'opacité d'une image. La valeur de l'argument indique le niveau d'opacité. Ainsi, une valeur de 0% rendra l'image complètement transparente et une valeur de 100% conservera l'image. Les valeurs intermédiaires appliqueront une opacité proportionnelle.  La valeur par défaut de l'argument est 1. Cette fonction est proche de la propriété opacity.

```CSS

filter: opacity(50%);

```

## Le filtre d'inversion

Ce filtre permet d'inverser les couleurs de l'image.La valeur de l'argument définit la force de cette inversion. Une valeur de 100% inversera complètement les couleurs (tel un négatif) et une valeur 0% conservera l'image. Les valeurs intermédiaires inverseront proportionnellement les couleurs de l'image. La valeur par défaut de l'argument est 0.


```CSS

filter: invert(50%);

```

## Le filtre de rotation de teintes

Ce filtre applique une rotation de teinte. La valeur de l'angle passé en argument définit le nombre de degrés parcouru sur le cercle des couleurs. Une valeur de 0deg conservera l'image telle quelle. La valeur par défaut du paramètre est 0deg. Il n'y a pas de valeur maximale pour l'argument, si une valeur supérieure à 360deg est utilisée, ce sera la mesure de l'angle correspondante qui sera utilisée.

```CSS

filter: hue-rotate(180deg);

```
## Appliqué plusieurs filtres

Pour cela rien de plus simple, il suffit d'enchainer les fonctions.
```CSS

filter: hue-rotate(180deg) brightness(50%);

```
## Le filtre animé

On peut animé un filtre en définissant les filtres et leur état à la fonction ``` @-webkit-keyframes filter-animation ``` à 0%,50% et 100%. Il suffit alors d'appliquer à la propriété ``` -webkit-animation ``` cette fonction avec une durée en seconde et un nombre de boucle d'animation à jouer.
```CSS
.ex10{
  -webkit-animation: filter-animation 5s infinite;
}

@-webkit-keyframes filter-animation {
  0% {
    -webkit-filter: sepia(0) saturate(2);
  }
  
  50% {
    -webkit-filter: sepia(1) saturate(8);
  }
  
  100% {
    -webkit-filter: sepia(0) saturate(2);
  }
}

```

## Le filtre appliqué derrière l'élément

Jusque là tous les filtres présentés précédement s'applique sur le background d'un élément HTML mais on peut appliquer un filtre derrière un élément (backdrop). Cela signifie que l'on est derrière le background.On peut donc appliquer un background sur l'élément et appliquer un filtre sur l'élément et son background. Pour cela il suffit de remplacer la propriété filter par la propriété backdrop-filter. L'effet étant situé derrière l'élément, il pourra être observé en ajustant la transparence de l'élément.
```CSS

filter:opacity(50%);
backdrop-filter: hue-rotate(180deg) brightness(50%);

```

## L'alternative des fichiers XML contenant un filtre SVG

La fonction url() prend comme argument l'emplacement d'un fichier XML qui définit le filtre SVG à appliquer. L'URL peut faire référence à une ancre d'un élément spécifique.
```SVG
// dans SVG

<svg ...>
	...
	<filter id="pictureFilter" >
		<feGaussianBlur stdDeviation="5" />
	</filter> 
</svg>
```
```CSS

filter:url(commonfilters.xml#pictureFilter);

```

### Sauf mention contraire, les fonctions qui acceptent des valeurs exprimées en pourcentages (34%) acceptent également des valeurs décimales (0.34).

# Les Blend mods

# Sources et autres tutoriels

- https://developer.mozilla.org/fr/docs/Web/CSS/filter
  
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
