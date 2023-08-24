# Les questions technique en Angular
## - C'est quoi angular ?
Angular est un framework JavaScript écrit en typeScript permet le développement des applications Web, open source créé par Google.

Il est utilisé pour créer des applications front end d'une seule page SPA(Single Page Application).

## - C'est quoi Angular CLI ?
Est un interface de ligne de commande. qui donne aux professionnels la possibilité pour ajouter des composants, les déployer instantanément et effectuer des tests et de nombreuses fonctions de ce type.

C'est quoi La différence entre un Framework et une Library ?
Library : c'est une boite des outils qu'on peut l'utiliser et qu'on peut contrôler.

Framework : c'est un cadre de travail, en d'autre terme c'est comme un laboratoire qui peut utilise les boites des outils(librarys), au contraire d'une librairie je peux pas contrôler tous, puisque le framework occupe la grande partie et moi je suis qu'un utilisateur et je ne suis pas l'administrateur.

## - C'est quoi La différence entre Angular et AngularJS ?
> Angular +2 :

- MVVM Model VIEW VModel - utilise les directives et les composants

- utilise le langage TypeScript, un sur-ensemble de JavaScript qui est typé statistiquement

- Angular offre un support mobile

- Sa structure simplifiée permet aux développeurs de maintenir facilement de grandes applications

***************************************************************************************************

> Angular JS :

- Il prend en charge le modèle Model-View-Controller ou MVC

- Il utilise JavaScript, un langage typé dynamiquement

- AngularJS n'offre pas de support mobile

- C'est relativement moins structuré.

## - C'est quoi JIT - Just-in-Time (Développement) ?
La compilation des templates se faite au niveau de navigateurs. Le mode par défaut quand on exécute 'ng serve' ou 'ng build'.

## - C'est quoi AOT - Ahead-Of-Time(Production)
La compilation se fait en avance, donc on a deux avantages.

Rendering plus rapide.

Détection d’erreurs en amout.

## - C'est quoi un composant en angular?
Un composant Angular est défini par une classe qui contient des propriétés et des méthodes pour manipuler les données et l'interface utilisateur de la partie de l'application gérée par le composant.

## - C’est quoi lifecycle hooks en Angular ?
Lors de la création d'une application Angular, il y aura des moments où nous devrons exécuter du code lors d'un événement spécifique, par exemple lorsqu'un composant est initialisé ou lorsque le composant est supprimé de l'écran :

ngOnChanges

ngOnInit

ngDoCheck

ngAfterContentInit

ngAfterContentCkecked

ngAfterViewInit

ngAfterViewCkecked

ngOnDestroy

## - Que sont les pipes en Angular ?
Sont des classes avec décoration @pipe, qui transforme l'entrée en sortie selon la logique donnée :

- pipe pure : appeler lorsque angular détécte un changement dans la valeur ou les paramétres passé au pipe.

- pipe impure : est appelé pour chaque cycle de détection de changement, que la valeur ou le(s) paramètre(s) change(nt), plus précisement lorsque Angular n'arrive pas à détécter les changement.

## - C'est quoi un template en angular?
Sont écrits à l'aide de HTML qui inclut des attributs et des éléments spécifiques à Angular. Sont combinés avec les données des API web, pour offrir à l'utilisateur une vue dynamique

## - C'est quoi ng-container en angular?
Le ng-container est un élément de syntaxe reconnu par l'analyseur Angular.

## - C'est quoi ng-template en angular?
La directive ng-template est utilisée dans Angular pour définir un contenu qui ne sera pas rendu immédiatement, mais qui pourra être utilisé plus tard comme modèle de rendu.

Cela peut être utile dans plusieurs situations, telles que : Créer un modèle de rendu qui sera utilisé plusieurs fois dans une vue.

## - C'est quoi un resolver Angular ?
Les Resolver en Angular permettent d'attendre le retour d'un observable avant d'initialiser / mettre à jour un composant après une mise à jour de l'url.

## - Que sont les Intercepteurs en Angular ?
Les intercepteurs font partie du module @angular/common/http et sont également utilisés pour inspecter et transformer les requêtes HTTP et les réponses HTTP( on implement l'interface HttpInterceptor qui contient la méthode intercept).

## - C'est quoi RxJS ?
C'est une implémentation JavaScript de standard ReactiveX permet de faire la programmation réactive (exemple : Observable).

## - C'est quoi NgRx ?
C'est une librairie implémentant le pattern Redux en utilisant la programmation réactive basé sur RxJS, permet à une application Angular de centraliser l’état de l’application, (Redux pour React).

C'est quoi package.json ?
npm installe le fichier package.json lorsqu'un nouvel espace de travail est créé, il comprend un ensemble de packages (Dependencies, DevDependencies)

## - C'est quoi json-server ?
librairie JavaScript qui permet de créer un serveur Nodejs pour générer une base de données au format JSON, utile juste lors de développement.

## - Comment je peux communiquer les composants en Angular ?
@Input / @Output

Un service (Subject) quand vous avez une hiérarchie complexe.

NgRx

## - C'est quoi les Directives en angular ?
Vous permets de modifier l'apparence, le comportement ou la disposition d'un élément DOM, existe trois types :

- Attribut Directives

- Structural Directives

- Component Directives

## - C’est quoi le data binding ?
ider le développeur à établir la communication entre le DOM et le composant :

Event binding

Property binding

String interpolation

Two-way data binding

## - C'est qoui Service en Angular ?
Pour partager la logique sur plusieurs components, par exemple les données des API web.

Promises and Observable ?
- Promises : émettent une seule valeur à la fois, ils s'exécutent immédiatement après la création

- Observables : émettent une séquence de données, ne sont exécutées que lorsqu'elles sont souscrites à l'aide de la méthode de subscribe(). ils aident à effectuer les opérations comme filter , map, pipe…

## - C'est quoi la différence entre Subject et BehaviourSubject ?
la principale différence entre Subject et BehaviorSubject réside dans le fait que BehaviorSubject nécessite une valeur initiale et émet toujours la dernière valeur émise à tout nouvel observateur qui s'abonne, tandis que Subject ne le fait pas et ne transmettra que les éléments émis après l'abonnement.

Imaginons le scénario suivant, dans le cas du Subject : je suis un observable, j'émet un événement, puis un observateur s'abonne. Cependant, cet observateur ne reçoit pas cet événement, car il s'est abonné après son émission. Il recevra uniquement les événements émis à l'avenir.

En revanche, dans le cas du BehaviorSubject, lors de l'abonnement, on reçoit le dernier événement, même si l'observateur n'était pas abonné au moment de l'émission de l'événement.

## - C'est quoi lazy loading en Angular ?
Le lazy loading (chargement différé) en Angular est une technique utilisée pour optimiser les performances des applications en chargeant les modules de manière asynchrone et au besoin, plutôt que de tous les charger au démarrage initial de l'application.

Cela permet de réduire le temps de chargement initial de l'application et de ne charger que les ressources nécessaires pour afficher la vue actuelle.