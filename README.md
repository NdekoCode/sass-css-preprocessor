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
