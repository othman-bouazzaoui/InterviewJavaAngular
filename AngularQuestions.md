# Les questions technique en Angular
## - C'est quoi angular ?
Angular est un framework JavaScript écrit en typeScript permet le développement des applications Web, open source créé par Google. Il est utilisé pour créer des applications front end d'une seule page SPA(Single Page Application).

## - C'est La différence entre Framework & Library ?
> Library : c'est une boite des outils qu'on peut l'utiliser et nous qui contrôle quand est ce qu'on peut faire ça et ça.

> Framework : c'est cadre de travail, en d'autre terme c'est comme un laboratoire qui peut utilise les boites des outils(laibrarys), au contraire d'une laibrairie je peux pas contrôler tous, puisque le framework occupe la grande partie et moi je suis qu'un utilisateur et je ne suis pas l'administrateur.

## - Quelle est la différence entre Angular et AngularJS ?
> Angular +2 :
 - MVVM Model VIEW VModel - utilise les directives et les composants
 - utilise le langage TypeScript, un sur-ensemble de JavaScript qui est typé statistiquement
 - Angular offre un support mobile
 - Sa structure simplifiée permet aux développeurs de maintenir facilement de grandes applications

 > Angular JS :
 - Il prend en charge le modèle Model-View-Controller ou MVC
 - Il utilise JavaScript, un langage typé dynamiquement
 - AngularJS n'offre pas de support mobile
 - C'est relativement moins structuré.

 ## - C'est quoi Angular CLI ?
  - Est un interface de ligne de commande. qui donne aux professionnels la possibilité pour ajouter des composants, les déployer instantanément et effectuer des tests et de nombreuses fonctions de ce type. 

## - C'est quoi RxJS ?
 - C'est une implémentation JavaScript de standard ReactiveX permet de faire la programmation réactive (exemple : Observable).

## - C'est quoi NgRx ? 
 - C'est une librairie implémentant le pattern Redux en utilisant la programmation réactive basé sur RxJS, permet à une application Angular de centraliser l’état de l’application, (Redux pour React).

## - C'est quoi package.json ?
 - npm installe le fichier package.json lorsqu'un nouvel espace de travail est créé, il comprend un ensemble de packages (Dependencies, DevDependencies)

## - C'est quoi json-server ?
 - librairie JavaScript qui permet de créer un serveur Nodejs pour générer une base de données au format JSON, utile juste lors de développement.

## - Comment je peux communiquer les composants en Angular ?
 - @Input / @Output
 - Un service (Subject) quand vous avez une hiérarchie complexe.
 - NgRx

## - C'est quoi les Directives en angular ?
> Vous permets de modifier l'apparence, le comportement ou la disposition d'un élément DOM, existe trois types :
 - Attribut Directives
 - Structural Directives
 - Component Directives

 ## - C’est quoi le data binding ? 
>  Aider le développeur à établir la communication entre le DOM et le composant :
#### o	Event binding
#### o	Property binding
#### o	String interpolation
#### o	Two-way data binding

## - C’est quoi Templates ?
- Sont écrits à l'aide de HTML qui inclut des attributs et des éléments spécifiques à Angular. Sont combinés avec les données des API web, pour offrir à l'utilisateur une vue dynamique

## C'est qoui Service en Angular ?
Pour partager la logique sur plusieurs components, par exemple les données des API web.

## - Promises and Observable ?
 - Promises : émettent une seule valeur à la fois, ils s'exécutent immédiatement après la création

 - Observables : émettent une séquence de données, ne sont exécutées que lorsqu'elles sont souscrites à l'aide de la méthode de subscribe(). ils aident à effectuer les opérations comme filter , map, pipe…

## - Bootstrap, comment on peut l’ajouter à Angular ?
> Bootstrap Est un framework JavaScript, CSS et HTML on peut l’ajouter :
##### Bootstrap CDN (Content Delivery Network) sans téléchargment.
##### Bootstrap NPM (Nods Package Manager), on dois le télecharger

## - C’est quoi lifecycle hooks ?
 - Lors de la création d'une application Angular, il y aura des moments où nous devrons exécuter du code lors d'un événement spécifique, par exemple lorsqu'un composant est initialisé ou lorsque le composant est supprimé de l'écran :
> 1 - ngOnChanges.<br>
> 2 - ngOnInit.<br>
> 3 - ngDoCheck.<br>
> 4 - ngAfterContentInit.<br>
> 5 - ngAfterContentCkecked.<br>
> 6 - ngAfterViewInit.<br>
> 7 - ngAfterViewCkecked.<br>
> 8 - ngOnDestroy. <br>

## - C'est quoi Angular pipes ?
> sont des classes avec décoration @pipe, qui transforme l'entrée en sortie selon la logique donnée : 
### - pipe pure : appeler lorsque angular détécte un changement dans la valeur ou les paramétres passé au pipe.
### - pipe impure : est appelé pour chaque cycle de détection de changement, que la valeur ou le(s) paramètre(s) change(nt), plus précisement lorsque Angular n'arrive pas à détécter les changement.

## - C'est quoi JIT - Just-in-Time (Développement) ?
- la compilation des templates se faite au niveau de navigateurs. Le mode par défaut quand on exécute "ng serve" ou "ng build".

## - C'est quoi AOT - Ahead-Of-Time(Production)
- la compilation se fait en avance, donc on a deux avantages.
> Rendering plus rapide.<br>
> Détection d’erreurs en amout.

## - Que sont les Intercepteurs en Angular ?
- Les intercepteurs font partie du module @angular/common/http et sont également utilisés pour inspecter et transformer les requêtes HTTP et les réponses HTTP( on implement l'interface HttpInterceptor qui contient la méthode intercept).





