# Le preprocesseur SASS

SASS est un preprocesseur que l'on retrouve dans pas mal de projet aujourd'hui et qui a l'avantage et qui a l'avantage d'integrer tout un tas des fonctionnalités qui vont vous permettre d'ecrire du CSS de maniere plus organiser et plus propre

L'idée avec SASS et que l'on peut avoir:

- Des variables
- On peut morceler notre CSS en plusieurs parties càd on peut importer un css qui sera ensuite mis dans le css principale cela est pratique pour decomposer notre code et eviter la repetition
- On peut aussi utiliser l'imbrication càd plutot que de réecrire à chaque fois chaque selecteur, vous pouvez utiliser l'imbrication pour selectionner les elements enfants de maniere plus simple et styler, cela permet d'avoir une structure un peu loqique quand vous ecrivez votre code
- On a des fonctionnalités un peu plus avancer comme les boucles, les conditions, l'heritage,  les fonctions, les mixins,....

On va essayer de passer en revus l'ensemble des fonctionnalités de SASS et comment on peux les utiliser

## Installation

Pour installer `SASS` le moyen le plus sure est d'utiliser le gestion de dependance de nodeJS càd `npm`, et pour cela il faut prealablement avoir installer nodeJS, ainsi pour installer SASS en utilisant `npm` on utilise la commande suivante
`npm install -g sass`

Apres cela vous pouvez maintenant coder en SASS et generer votre fichier CSS à la fin, pour generer un fichier CSS on utilise la commande suivante
`sass PAthToSASSFile PathToCSSFile` par exemple `sass assets/scss/app.scss assets/css/style.css`, avec cette commande SASS va compiler son code et va generer un fichier `CSS`, si le dossier existe mais que le fichier styles.css n'existe pas, SASS va créer ce fichier

## A quoi sert le fichier map

Le ficher `.css.map` est un fichier qui est generer par SASS lorsque l'on compile le code à fin de generer un fichier CSS, ce fichier map va permettre d'indiquer aux navigateur la correspondance entre une ligne CSS et une ligne SCSS, grace à ce fichier .css.map le navigateur peut savoir à quel ligne à été écrit une regle spefique dans le fichier `scss` ou `sass`, ce fichier nous permet de trouver la correspondance et de pouvoir voir les erreurs dans notre fichier source original si il y en  et pas forcement dans le fichier `css` qui a été compiler, c'est un outils très important pendant le developpement que on enlevera pendant la mise en production

## Les fonctionnalités de SCSS ous SASS

### L'import des fichiers

On peut avoir un fichier `scss` ou `css` qui nous est utilise dans notre fichier stylisation, avec SASS on peut l'importer en utilant la syntaxe `@import "PathToTheCSSOrSCSSFileToImport"` par exemple `@import "libs/reset.scss"`

### Imbrication(Nested Rules)

Le principe d'imbrication avec SCSS, le principe est que l'on va pouvoir imbriquer des regles CSS ou des elements CSS les une dans les autres pour eviter la repetition
![Imbrication SCSS](/assets/img/Imbrication-SCSS.PNG)
![Imbrication SCSS](/assets/img/Imbrication-SCSS-2.PNG)

### La notion d'heritage

Le principe de l'heritage c'est de dire que une balise ou un selecteur va agir comme un autre selecteur
Cela permet de definir des comportement génériques sur les selecteurs ou les proprieter, pour dire que un selecteur ou une proprieter herite des comportement d'un autre on utilise le mot clé `@extend`
