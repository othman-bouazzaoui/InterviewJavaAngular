# Les questions technique en JAVA
## C'est quoi Java ?
 - Java est un langage de programmation orienté objet créé par James Gosling et Patrick Naughton, employés de Sun Microsystems, avec le soutien de Bill Joy, présenté officiellement le 23 mai 1995 au SunWorld. La société Sun a été ensuite rachetée en 2009 par la société Oracle qui détient et maintient désormais Java.

Nb : java n'est pas Orienté Objet à 100%, vu qu'il y a des types primitif (ex int, float, long).

## C'est quoi JDK, JRE et JVM ?
  - JDK : JAVA DEVELOPPEMENT KIT :=> permet au developpeur de compiler un projet JAVA + les outils de developpement ....
  - JRE : JAVA RUNTIME ENVIRONEMENT :=> permet au developpeur d'avoir quelque outils de developpement + l'execution des application (ex : java -jar xxx.jar).
  - JVM : JAVA VIRTUEL MACHINE :=> permet au byt-code de fonctionner correctement dans n'import quel plateforme

## Comment Java fonctionne ?
 - on écrit le code java dans un fichier text avec l'extention .java
 - puis on le compile .java pour qu'il devient .class => byte-code prét pour JVM ex javac Test.java, puis java Test pour l'executer
 - donc Il faut installer Java Virtual Machine qui va traduit le byte-code en langage comprhensible.

## Est-ce qu'il y a des mots résèrver en JAVA ?
  Oui, il y a plusieurs mot qu'on doit l'utiliser surtout la déclaration des attributs ou les méthodes ou les classe (ex class, int, void, final ...)
   - class : c'est une template qui represente un type des données.
   - objet : c'est l'instanciation d'une classe
   - methode: c'est l'action(comportement) qui peut faire un objet.

## Quelle est La convention de nomination dans Java ? 
  * Packages : generalement c'est le nom de domaine d'entreprise suivi par nom ex : com.tawdi7atnet.models
  * Class : On commence avec un majuscule + la notion CamelCase.
  * Attributs : on commence par miniscule + la notion CamelCase.
  * Constant : MAJUSCULE
  * methodes : on commence par miniscule + la notion CamelCase.

  ## Comment je peux importer une package ?
  - import packageName.* ou le nom de la classe souhaitée.

## Comment je peux reduire la visibilité ?
  - public : je peux accéder comme je veux.
  - protected : je peux accéder depuis mon class, class fille, même package 
  - private : défini seulement dans la classe
  - default : défini seulement dans les classes qui se trouvent dans le meme package

  ## C'est quoi le main en JAVA ?
  - Le main c'est le point d'entrée d'une application JAVA.
  - public: c'est à dire qu'on l'appeler hors cette classe.
  - static: on l'invoque sans instanciation
  - void : ne return aucune valeur
  - String [] : accepte un tableau des string (args)

  ## C'est quoi la différence entre la surcharge et redifinition ?
    - Surcharge => creation d'une methode dans la meme class avec l'ajout d'un parametre 
    - redefinition => nécéssite l'héritage et créer une methode par la meme nom et on peut changer le contenu ,on peut pas reduire la visibilité

## Parlez-nous sur l'utilisation le mot final en JAVA ?
    final => Attribut,Class,Methode:
             => les class  : desactiver l'heritage.
             => les methode: desactiver la redefinition.
             => les attributs: lorsque on veut definir une constante, il doit etre initialiser.
     l'ordre d'initialisation :
           1- lors de la declaration.
           2- Dans un bloc d'initialisation.
           3- Dans un constructeur.

## Qu'est ce que signifie le mot ABSTRACT en Java ?
C'est de créer une class abstract avec au moin une methode abstract mais on ne doit pas défini son corps.
l'objectif aussi d'oblige que les class filles défini cette methode.

## Qu'est ce que signifie le mot interface en Java ?
- C'est un contrat entre un fournisseur et un client pour que le client voir la signature(interface) 
- Cous les elements d'une interface sont public et abstract meme que ne les voit pas .
- On peut declarer des attributs final(constant) et l'initialisé.

## Qu'est ce que signifie la serialisation et déserialisation ?
    - serialisation : sauvegarder un obj en octéts, puis l'ecrire dans fichier
    - deserialisation : convert un fichier en octet, puis le convertir vers obj
sérializer un objet consiste à le convertir en un tableau d'octets, que l'on peut ensuite écrire dans un fichier, envoyer sur un réseau au travers d'une socket etc... Ce mécanisme existe depuis les débuts de l'API Java I/O, et il est très pratique.

## C'est quoi les collections en Java ?
    est un ensemble de classes et d'interfaces qui implémentent des structures de données de collection couramment réutilisables. Bien que référencé comme un framework, il fonctionne à la       manière d'une bibliothèque.

     - List accept les doublons et conserver l'arrangement de list.
     - Set n'accept pas les doublons ne conserver pas l'arrangement, on peut comparer les objet on se basons sur son Hashcod(public int hashCode()) et si un egale l'autre on passe vers la method equals(public boolean equals(Object o)) pour comparer les valeurs, si true il considere que les deux sont doublons si non il va le stocker.
     - Set ----- HashSet
     * n'accepte pas les doublons
     * Ne respecte pas l'ordre
     * Deux objets sont doublons
        - s'ils ont le même hascode
        - si leur méthod equals return true

     - Set ----- TreeSet
     * n'accepte pas les doublons
     * Deux objets sont doublons
      - s'ils ont le même hascode
      - si leur méthod equals return true
     * faire le trie par implements Comparable (1 seul critére) compareTo

     -Map -----  Mapset
     n'accepte pas les doublons et prends 2 elements(key, value) et se compose de la Set .
     
     LinkedHashMap vs HashMap
     HashMap : implement l'interface Map, ne garanti pas l'ordre d'insertion
     LinkedHashMap : c'est une class fille de HashMap, elle garanti le tri d'insertion

## Qu'est ce que signifie les class .properties ?
  - Class.properties : c'est une class pour stocker les clés avec ses valeurs.
  - RessourceBandle : class pour lire les clés avec les valeurs de la class .properties

## C'est quoi les exceptions en JAVA ?
   Les exceptions représentent le mécanisme de gestion des erreurs intégré au langage Java. Il se compose d'objets représentant les erreurs et d'un ensemble de trois mots clés qui permettent de détecter et de traiter ces erreurs (try, catch et finally ) mais aussi de les lever ou les propager (throw et throws) :

     - throws: en les declare coté signature
     - throw :  en les declare coté bloc

## Les memoires en JAVA ?
    - Stack = pil : là où se trouve les références 
    - heap = le tas : là ou se trouve les détails d'objet.

## c'est quoi La différence entre == & equals ?
    - == c'est un opérateur, qui test les valeurs stocké dans le pil(stack) si égaux ou non
    - equals c'est une méthode qui test le contenu de l'objet quel que soit en stack ou heap.

## Qu'est-ce qu'un objet immuable ? 
- Tu ne peux pas modifier les objets d'une classe immuable une fois qu'ils sont créés. En d'autres termes, une fois que tu les crées, tu ne peux pas les modifier. Si tu essaies de modifier un objet immuable, tu obtiendras un nouvel objet (clone) et tu modifieras ce clone pendant sa création.
- le contraire c'est mutable.

## La différence entre String & StringBuilder & StringBuffer ?
- String est un objet ummuable, Cela signifie que tu ne peux pas modifier son contenu après création.
- StringBuilder & StringBuffer : sont des classes mutables, et tu peux donc les modifier plus tard. Si nous essayons de modifier le contenu d'un objet String, la JVM crée une nouvelle  chaîne, laissant celle d'origine non modifiée. C'est pourquoi les performances sont meilleures avec StringBuffer qu'avec String.
- La principale différence entre StringBuffer et StringBuilder est que les méthodes de StringBuffer sont synchronisées, alors que celles de StringBuilder non.

## C'est quoi JDBC ?
### [JDBC = Java DataBase Connectivity]
  * L’API JDBC est une API pour accéder à différentes bases de données relationnelles.
    * Vous l’utilisez pour accéder à des bases de données relationnelles sans intégrer une dépendance à un type de base de données spécifique dans votre code.
    * JDBC signifie Java DataBase Connectivity.
    * L’API JDBC fournit l’abstraction et les pilotes JDBC fournissent l’implémentation. De nouveaux pilotes peuvent être connectés à l’API JDBC sans modifier le code client.
    * La classe DriverManager gère la liste des pilotes de base de données dans JDBC.

## Statement en JDBC ?
   * Statement encapsule une instruction SQL qui est transmise à la base de données pour être analysée, compilée, planifiée et exécutée.
    * PreparedStatement en Java améliore les performances et empêche également l’injection SQL.
    * CallableStatement est utilisé dans JDBC pour appeler une procédure stockée à partir d’un programme Java.


