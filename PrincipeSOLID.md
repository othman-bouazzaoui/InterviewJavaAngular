# Identifiez les principes SOLID 
Chaque lettre de l'acronyme SOLID représente un mantra à répéter pour concevoir l'architecture de votre système. Au fur et à mesure du cours, nous les analyserons chacun en détail. Nous les mettrons également en pratique en concevant une application simple de jeu de cartes.

# S.O.L.I.D, qu’est-ce que ça peut bien vouloir dire ?

## « S » correspond au principe single responsibility (responsabilité unique).
Une classe ne doit faire qu'une seule chose et elle doit bien la faire. Elle ne doit avoir qu'une seule raison de changer.

## « O » correspond au principe open/closed (ouvert/fermé).
Une classe doit être ouverte à l'extension, mais fermée à la modification.

Eh bien, lorsque vous ajoutez un nouveau concept au système (une fonctionnalité), vous ne devriez pas avoir à revenir en amont et à effectuer tout un ensemble de modifications sur l’existant pour qu’il puisse supporter le code de la nouvelle fonctionnalité.

## « L » correspond au principe de substitution de Liskov.
L'ajout d'un sous-type par héritage ne doit pas rompre le code existant. C'est ce que j'appelle le principe « zéro surprise ». En d'autres termes, si le système fonctionne et que j'ajoute une nouvelle classe héritée d'une autre, le système doit continuer de fonctionner.

## « I » correspond au principe interface segregation (ségrégation des interfaces).
Il s'agit pour l'essentiel du principe de responsabilité unique appliqué aux interfaces.

## « D » correspond au principe dependency inversion (inversion des dépendances).
Les classes de haut niveau ne devraient pas avoir à être modifiées lorsqu'une classe de bas niveau est modifiée. Les classes de haut niveau doivent définir une abstraction à laquelle se conforme la classe de bas niveau.

Nous mettrons en œuvre chacun de ces principes en Java. Intéressons-nous tout d'abord à la façon dont ils sont implémentés  dans une architecture connue et reconnue : l’architecture modèle-vue-contrôleur (MVC). Nous avons choisi de nous appuyer sur la structure MVC, car elle est en phase avec les principes SOLID.

En résumé
Une conception simple, réfléchie et intentionnelle amène à un code facile à comprendre, modifier et tester. 

L'application des principes SOLID est une ligne directrice pour ce type de conception.

Les principes SOLID sont les suivants :

# responsabilité unique ;

# principe ouvert/fermé ;

# substitution de Liskov ;

# ségrégation des interfaces ;

#  inversion des dépendances.