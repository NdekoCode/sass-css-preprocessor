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

On peut avoir un fichier `scss` ou `css` qui nous est utilise dans notre fichier stylisation, avec SASS on peut l'importer en utilant la syntaxe `@import "PathToTheCSSOrSCSSFileToImport"` par exemple `@import "libs/reset.scss"`, quand vous importer un fichier vous importer toutes les variables, les fonctions, les propriétés qui sont à l'interieur.

### Imbrication(Nested Rules)

Le principe d'imbrication avec SCSS, le principe est que l'on va pouvoir imbriquer des regles CSS ou des elements CSS les une dans les autres pour eviter la repetition
![Imbrication SCSS](/assets/img/Imbrication-SCSS.PNG)
![Imbrication SCSS](/assets/img/Imbrication-SCSS-2.PNG)

### La notion d'heritage

Le principe de l'heritage c'est de dire que une balise ou un selecteur va agir comme un autre selecteur
Cela permet de definir des comportement génériques sur les selecteurs ou les proprieter et ainsi permettre de ne pas trop se repeter, pour dire que un selecteur ou une proprieter herite des comportement d'un autre on utilise le mot clé `@extend` suivis du selecteur dont vous voulez etendre

![Heritage](/assets/img/heritage.png)

On peut l'utiliser de façon simple ou de façon plus generique en utilisant des faux selecteurs qui commencent par un `%`

![Heritage en utilisant un selecteur generique](/assets/img/Heritage-2.png)

### Les variables

Pour declarer une variable dans `SASS` on utilise les memes règles que dans le language `PHP` càd avec un signe `$` par exemple `$space: 12px` ou `$medium-up: "only screen and(max-width: 768px)"`
Si dans une variable vous avez des chaines de caracteres qui contient des contenus css convertissable pour convertir ce contenus il faudra l'entourer d'un `#` suivis d'une accolade

![interpollation des variables](/assets/img/interpollation-variables.png)

On peut se demander dans les variables quelle est la priorité, qui gagne, qu'est-ce qui se passe si j'ai deux variable qui on le meme nom mais qui sont declarer à plusieurs endroit differents
Si une variable est definis à plusieurs endroit c'est la derniere definitions qui l'importe
Mais si vous ajouter un un `!default` après la valeur de la variable alors cette variable prendra sa valeur si cette variable n'as pas eté definit au préalable ie si elle n'est definit et initialiser avec une valeur null autre par ailleurs
Cela peut permettre de definir les regles de base par exemple

Dans l'utilisation des variables on peux aussi voir les fonctions, les fonctions vous permettent d'effectuer quelques petites operations qui peuvent etre plus ou moins utile suivant la situation, parmis les fonctions utiles on a les fonctions

`darken` et `lighten` qui nous permettent respectivement d'assombrir ou d'eclaircir une couleur, ces deux fonctionss fonctionnent un peu de la meme maniere ils prennent en premiers parametres la couleur sous forme d'une variable ou d'une valeur en format de couleur acceptable et en second parametres de combien on veut assombrir ou eclaircir.

![Fonctions natifs SASS](/assets/img/darken-lighten.png)
