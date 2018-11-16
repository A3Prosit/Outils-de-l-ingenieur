# Prosit 4 : Outils de l’ingénieurs

## Team :

Animateur : Gilly

Secrétaire : Fantou

Scribe : Neuville

Gestionnaire : Dorian

## Mot clés (* à def) :

- TDD*

- SOLID*

- UML*

- Design Pattern* : arrangement caractéristique de modules reconnu comme bonne pratique en réponse à un pb de conception d'un logiciel.

- IDE

- Qualité du code* : 

- Qualité logiciel* : 

- 6 épreuves

- Solution appropriée

- Prédiction de la solution

- Concevoir

- Développement

- Ingénieur

- Outils*

## Contexte :

Quoi ?

- Dev comme un ingénieur

Comment ?

- Utiliser des Design Pattern

- Utiliser différents outils de conceptions (Tests)

- Sans lancer son code

Pourquoi ?

- Pour obtenir une solution appropriée et fonctionnelle

- Pour gagner du temps

- Pour avoir un code optimisé

## Contraintes :

- 2 jours et demi

- Ne pas lancer le programme

- Ne pas fumer !!

## Problématique :

- Quels sont les outils de conception de l’ingé info ?

- Comment coder proprement en utilisant les Design Pattern ?

- Comment structurer, concevoir et vérifier son code ?

## Généralisation :

- Concevoir (CDIO)

- Outils

- Outils de conception

- Conception et optimisation

- Qualité

## Hypothèses :

- Il va falloir faire des UML

- Les DP permettent de structurer le code

- Le TDD (Test Driven Protocol) est toute la partie test du code

- Le TDD permet de prédéfinir les fonctionnalités futures du programmes

- SOLID est une méthode en 5 phases (Chaque lettre)

## **Plan d’action (Attention à la charge de travail)**

## Etudes :

### DP

Design pattern aka patron de conception: arrangement caractéristique de modules reconnu comme bonne pratique en réponse à un pb de conception d'un logiciel.

Antipattern: anti-patrons, erreurs courantes de conception des logiciels. Leur nom viens du fait que ces erreurs sont apparues dès les phases de conception par l'absence ou mauvaise utilisation des design patterns
Les anti-patrons se caractérisent souvent par une lenteur excessive du logiciel, des coûts de réalisation ou de maintenance élevés, des comportements anormaux et la présence de bugs.

Il existe également les  GreyPatterns  (dont le bénéfice ou les inconvénients ne sont pas clairement établis).


Gang of Four: 23 DP classic en software design
dev par Erich gamma, Richard Helm, Ralph Johnson et John Vlissides aka the Gang of Four
on les retrouve dans "Design Patterns: Elements of Reusable Object-Oriented Software"

on peut les diviser en 3 groupes:
- creational patterns : abstract factory, builder, factory method, prototype, signleton
- Structural patterns: adapter, bridge, composite, decorator, facade, flyweight, proxy
- Behavorial patterns: chain of responsibility, command, interpreter, iterator, mediator, memento, observer, state, strategy, template method, visitor

ces paterns fournissent une interface pour créer des familles d'objets liés ou dépendents sans avoir à créer de classe contrete (on fait des abstract et ensuite les concrete et les concrete sont liés par ça)

**Abstract factory**
fournis une interface pour créer des familles d'objets liés ou dépendents sans spécifier de classe concrète.

**Builder:**
 sépare la construction d'un objet complexe de sa représentation pour que le même procédé de construction puisse créer différentes représentations
diff avec abstract factory: avec abstract factory le client utilise la factory pour créer l'objet: il est responsable el'interactin entre les classes, avec builder le client demande au Director de créer l'objet: il ne sait pas comment les classes interagissent

**Factory method:**
défini une interface pour créer un objet mais laisse ls sous-classes décider quelle classe instancier. 

**Prototype**
spécifie les types d'objets à créer en utilisant une instance prototypique et créé de nouveaux objets en copiant ce prototype

**Singleton:**
assure qu'une classe n'a qu'une seule instance et fournis un moyen d'accès

**Adapter:**
Fournis une inteface pour créer des familles d'objets related ou dépendants sans spécifier de classe concrète

**Bridge:**
découple une abstraction et son im^lémentation pour qu'elles puissent varier indépendement.

**Composite:**
compose des objets en structure d'arbre pour pouvoir représenter des hiérachies partielles. Cela permet au client de traiter les objets and la composition des objets uniformément

**Decorator:**
attaches des responsabilités aux objets dynamiquement,il fournit une altrenative flexible aux sous-classes

**Facade:**
fournit une interface unifiée d'un ensemble d'interfaces dans un sous-système

**Flyweight:**
utilise le partage pour supporter un grand nombre d'objets qui ont une partie de leur état interne en commun et une partie qui peut changer

**Proxy:**
propose un remplaçant d'un objet pour en contrôler l'accès

**Chain of responsibility:**
évite le coupling entre émetteur d'une requête et récepteur en donnant à l'objet plus d'une chance de gérer la requête. Chaine les recepteurs et passe la requête le long de la chaine jusqu'à ce que l'objet le gère

**Command:**
encapsule une requete en tant qu'objet ce qui nous permet de parametrer les clients avec différentes requetes, queue, log requests et suporter des opération infaisables "This pattern encapsulates a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undoable operations."

**Interpreter:**
pour un langage donné, défii une représentation de sa grammaireet un interpréteur utilisant cette représentation pour interpréter les phrases de ce langage

**Iterator:**
fournis un moyen d'accéder aux éléments d'un objet aggrégé de façon séquentielle sans exposer la représentation sous-jacente

**Mediator:**
Défini un objet encapsulant comment un ensemble d'objet interagit. Il promeut? le couplage faible en empéchant aux objets de se référer les uns les autres explicitement et permet de varier les interactions indépendement

**Memento:**
capture et externalise l'état interne d'un objet sans violer l'encapsulation pour qu'il puisse être rétauré à cet état plus tard

**Observer:**
défini une relation one-to-many entre les objets pour que lorsque létat de l'un change, les observeurs soient notifiés automatiquement

**State:**
permet à un objet de changer son comportement lorsque son état interne change, on aura l'impression qu'il change de classe

**Strategy:**
défini une famille d'algo qui s'encapsulent et les rend interchangeables. Laisse l'ago varier indépendement des clients qui l'utilise.

**Template method:**
défini le squelette d'un algo dans une opération, sais-traitant certaines opération aux sous-classes. La sous-classe peut redéfinir certaines étapes pour changer la structure de l"algo

**Visitor:**
représente une opération a être effectuée sur les éléments faisant partie de l'objet. Cela permet de définir une nouvelle opération sans changer la classe des élément sur laquelle elle opère.


### TDD (Java + C#)

Dévelopement piloté par les test, repose sur le Test First, une méthode agile intitulée Extreme Programing aussi appelé XP
XP à été mise au point dans les 90spar Kent Beck , Ward Cunningham et Ron Jeffries mais elle nait offficiellement en 99 avec "Extreme Programming Explained"

L'écriture des test automatisés dirige l'écriture du code source. très efficace pour livrer des logiciels biens contruits avec des tests de non-régression.
base du processus de dv Agile qui met l'accent sur la livraison rapide et féréquent de composants logiciels fonctionnels. 
Les tests unitaires automatisés écrits en TDD et les tests d'acceptation automatisés écrits en premier sont des pratiques incontournables qu'une bonne équipe de développement logiciel Agile doit maîtriser.

méthode TDD:
on code le test
on code pour passer le test puis on refactor, il s'agit d'un autre principe de l'Extreme Programming

la démarche à suivre pour mettre en place cette méthode est décomposée en trois phases: RGR (aussi appelé la Mantra) <-(comme dans un mantra?...)

R : écrire un code de test et le faire échouer
G : écrire le code métier qui valite le test
R:  refactore le code

le cycle de dev préconisé par le TDD comporte 5 étapes:

- écriture d'un premier test
- Exécuter le test et vérifier qu'il échoue
- Ecrire l'implémentation pour faire passer le test
- Exécution des tests afin de vérifier qu'ils passent
- Remaniement (Refactor) du code afin d'en améliorer la qualité en conservant les mêmes fonctionnalités (on clean le code moche...)

et on recommence avec un nouveau test


avantages:
- les test unitaires sont vraiment écrits, on ne les retarde pas jusqu'à ne jamais les faire
- force la clarification des détails de l'interface et du comportement car on doit y réfléchir au préalable pour écrire le test
- vérification démontrable, répétable et automatisée
- non régression puisqu'il faut passer les anciens tests
- facilite le débogage si on peut le reproduire avec un test
- permet de comprendre du legacy code:
	- écrire un test pour une foncionnalité qu'on souhaite comprendre
	- exécuter le test et verif qu'il échoue
	- modifier le test jusqu'à ce qu'il se valide

Fitness : composé d'un wiki qui référence les scénarios de test, un moteur d'exécution pour extra

### UML

Unified Modeling Language langage de modélisation à base de pictogrammes conçu pour fournir une méthode normalisée pour visualiser la conception logicielle, couramment utilisé en dev logiciel et conception orientée objet

Il est le résultat de la fusion des précédents langages de modélisation précédents: Booch, OMT, OOSE. Il est maintenant un standard adopté par l'Object Management Group(OMG)

il est utilisé pour visualiser, modifier et construire les documents nécessaires au bon developpment d'un logiciel orienté objet. Les différents éléments représentables sont :
- activité d'un objet/logiciel
- acteurs
- processus
- schéma de base de données
- composants logiciels
- réutilisation de composants

on peut extraire du code d'un UML

symboles:
cf google/ta mémoire/ wikipedia trop d'image a mettre dans un .md j'ai la flemme
- classe (carré avec les attributs et les opération)
- objet (carré avec les attributs et les opération)
- paquet (dossier)
- interface o<--- sens du flux de l'interface, O)-- est un raccourci pour la superposition de -->o et o<--
- dépendance --->
- généralisation généralisation --|> (flèche pleine)
- association : 
	- agrégation --<>
	- composition --<> plein
- réalisation (---> ?)
- utilisation (--> aussi ?)

ordre général de création des digrammes:
- diag de cas d'utilisation														   _
- diag de séquence																    |  spécification, cahier des charges
- diag d'activité (processus métiers)									    |
- diag d'activité (cinématique et/ou processus applicatifs)  _|
- diag de classe																		_
- diag d'objet																			 |
- diag de communication														 |  conception architecturale
- diag de déploiement															 |
- diag de composants														   _|

classe: le seul qui est obligatoire

### Qualité du code → SOLID

acronyme représentant cinq principes de bases de la POO introduits par Michael Feathers et Robert C. Martin au début des années 2000. Ils sont censé apporter une ligne directrice permettant le dev de logiciels plus fiables et robutes.

S:  **S**ingle responsibility principle, responsabilité unique: une classe, une fonction ou une méthode doit avoir une et une seule responsabilité
O: **O**pen/Closed principle: Ouvert/fermé: une classe doit être ouverte à l'extension mais fermée à la modification (on peut hérite, pas modifier?)
L: **L**iskov substitution principle, Subsitution de Liskov, une instance de type T doit pouvoir être remplacée par une instance de type G, tel que G sous-type de T, sans que cela ne modifie la cohérence du programme (si on remplace une classe prarente par un enfant la cohérence est préservée)
I: **I**nterface segregation principle, ségrégatio des interfaces: préférer plusieurs interfaces spécifiques pour chaque client plutôt qu'une seule interface générale
D: **D**ependency inversion principle,inversion des dépendences: il faut dépendre des abstractions pas des implémentations



## Réalisation :

### Corbeille → 6 épreuves (Sans lancer le programme)

### Concevoir et tester la corbeille
