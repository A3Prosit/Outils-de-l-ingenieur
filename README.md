
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

- Design Pattern*

- IDE

- Qualité du code*

- Qualité logiciel*

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

### TDD (Java + C#)

### UML

### Qualité du code → SOLID

## Réalisation :

### Corbeille → 6 épreuves (Sans lancer le programme)

### Concevoir et tester la corbeille


## Les Design Pattern

- Patron de conception
- Arrangement caractéristique de module, reconnue comme "bonne pratique" pour répondre à un problème de conception logiciel --> Influence sur l'architecture.
- Issu de l'expérience des concepteurs de logiciels
- Il en existe 23 :
	- Factory & Abstract Factory
	- Adapter
	- Bridge
	- Builder
	- Chain of responsibility
	- Command
	- Composite
	- Decorator
	- Façade
	- Factory Method
	- Flyweight
	- Interpreter
	- Iterator
	- Mediator
	- Memento
	- Object Pool
	- Observer
	- Prototype
	- Proxy
	- Singleton
	- State
	- Strategy
	- Template method
	- Visitor
	- Modèle Vue Contrôler (MVC)

"Antipatterns" : Erreurs courantes de conception logiciels : 
- Lenteur excessive du logiciel
- Coûts de réalisation ou maintenance élevés
- On retrouve :
	- Abstraction inverse
	- Action à distance
	- Ancre 
	- Ancre de bateau
	- Attente active
	- Interblocages & famine
	- Programmation spaghetti
	- Réinventer la roue
	- Surcharge des interfaces
	- Objet divin
	- Vous n'en aurez pas besoin
	- {...} : https://fr.wikipedia.org/wiki/Antipattern

## TDD - Java & C#

- Méthode de développement agile

![](http://igm.univ-mlv.fr/~dr/XPOSE2009/TDD/img/PresentationTDDPrincipeBaseAvecTDD.jpg)
 - Méthode TDD consiste à écrire des tests unitaires avant de procéder à une phase de codage 
- Trois phases pour mettre en place la méthode appelé RGR (ou mantra)
	- R (Red) = code de test et le faire échouer
	- G (Green) = écrire le code métier qui va valider le test
	- R (Refractor) = Remanier le code pour en améliorer la qualité
- Cycle de développement :
	
![](http://igm.univ-mlv.fr/~dr/XPOSE2009/TDD/img/PresentationTDDCycleDeveloppement.jpg)
**Avantages**
- Tests unitaires réellement écrits (sinon ils n'y sont jamais)
- Code plus cohérent, satisfaction du développeur à avoir du "vert" partout
- Clarification des détails de l'interface et du comportement : Écrire seulement le code utile.
- Vérification démontrable
- Non présence de dégression (pas d'impacts)

### Le TDD en Java :
- Junit est la bibliothèque de test
![](http://igm.univ-mlv.fr/~dr/XPOSE2009/TDD/img/ExempleTDD1.jpg)- On écrits @Test pour débuter l'écriture d'un test
- Des fonctions utiles comme "assertEquals"(deux valeurs) ; equals (deux objets) permettent faire des comparaisons
- Une barre de couleur permet de tester la validé R/V
- Catch-Exception ⇒ On écrit un test, où l'on va catch l'exception déclenché; si l'exception se lève bien on va assert son message pour valider le test.
````Java
`@Test`
`public` `void` `exp0_should_throw_exception_when_calculating_square_root_of_negative_number(){`
`try` `{`
`calculator.squareRoot(-``10``);`
`fail(&quot;Should` `throw` `exception when calculating square root of a negative number&quot;);`
`}``catch``(IllegalArgumentException aExp){`
`assert``(aExp.getMessage().contains(&quot;negative number&quot;));`
`}`
`}`
````
ou 
`@Test expected = LaClassDeNotreException` à déclarer avant


![](http://igm.univ-mlv.fr/~dr/XPOSE2009/TDD/img/ExempleTDD10.jpg)
### C#
- Quand on fais un nouveau projet --> Projet de test unitaire
	- Génère uue classe de test
	- [TestMethod] est écrite au dessus de chaque test
	- Assert.Arequal() pour tester les valeurs
	- Assert.IsTrue()
	- Assert.IsNull()
	- Tester les valeurs :
```C#
[TestMethod]
[ExpectedException(typeof(FormatException))]
public void ToInt32_AvecChaineNonNumerique_LeveUneException()
{
    Convert.ToInt32("abc");
}
`````
⇒ Exécuter -> Tous les tests : On peut voir les tests réussis et échoués.

## SOLID

- 5 Principes de base, apportant une ligne directrice permettant un développement logiciel fiable et robuste.
- On parle de "violation" si l'une des règles n'est pas respectée

- **Single Responsability :** Une classe, une fonction, ou une méthode doit avoir une et une seule responsabilité.
		- CRC cards : Outils de brainstosrming pour desgin de l'orienté objet
```php
$shapes = array(
    new Circle(2),
    new Square(5),
    new Square(6)
);

$areas = new AreaCalculator($shapes);
//Créer une classe plutôt qu'une fonction dans AreaCalculator
$output = new SumCalculatorOutputter($areas); 

echo $output->JSON();
echo $output->HAML();
echo $output->HTML();
echo $output->JADE();
```
- **Open/Closed :** Une classe doit être ouverte à l'extension, mais fermée à la modification
	- Permet d'éviter la régression suite à l'ajout de nouvelles fonctionnalités
	- Modifiable que part extension, sans modification du code source
	- On doit donc faire de l’abstraction (interface) ou polymorphisme

- **Liskov Substitution :** Une instance de type T doit pouvoir être remplacée par une instance de type G, tq G sous-type de T, sans que cela ne modifie la cohérence du programme :
	- Exemple du carré "extands" rectangle
		- Si plus de rectangle ⇒ Plus de carré
		- Solution : Créer une classe qui pourra construire les deux, avec des méthodes abstraites
		- On peut utiliser la conception par contrat (Desgine By Contract - DBC) qui est une approche pur détecter les violations du principe de Liskov.
		- Des langages comme "Eiffel" propose nativement ce type de conception
		
- **Interface Segregation :** Préférer plusieurs interfaces spécifiques pour chaque client plutôt qu'une seule interface générale.
		- Créer plusieurs petites interfaces plutôt qu'une seule
		- Facilite les tests unitaires, décomposition du code, meilleure compréhension générale
		- /!\ Ne pas faire d'interface pour chaque classe

- **Dependency inversion** : Il faut dépendre des abstractions, pas des implémentations
		- On créer des abstractions pour faire des 'injection de dépendance' entre deux "blocs dépendants"
		- Permet d'être souple en cas de changement d'un des deux partis
		- Facile les tests
		- Gestion des objets de manière responsive

## UML

UML - Unified Modeling Language - Langage de modélisation graphique à base de pictographes pour visualiser la conception d'un système.
- Utilisé en développement logiciel & conception orientée objet

On retrouve :
**Diagramme de structure ou diagramme statiques** : 

- Diagramme de classe : représentation des classes dans un système
- Diagrammes d'objet : Représentation des classes (objet) dans un système
- Diagramme composant : Composant d'un point de vue physique (fichiers / bibliothèques / BDD)
- Diagramme de déploiement : Elements matériels (Ordi/ périph réseau) et la manière dont les compos systèmes sont répartis & ils interagissent entre eux
- Diagramme des paquets : Paquets (conteneur), ensemble de définition
- Diagramme de structure composite : Boîte blanche, les relations entre composants d'une classe
- Diagramme de profils : Personnalisation pour un domaine particulier

**Diagramme de comportement**
- Diagramme cas d'utilisation : Possibilités d'interaction entre le système et les acteurs, càd toutes les fonctionalités
- Diagramme états-transitions : sous forme de machine à états finis, le comportement du système ou de ses composants
- Diagramme d'activité : Sous forme de flux, le comportement du système ou de ses composants

**Digramme d'interaction ou diagrammes dynamiques**
- Diagramme de séquence : Façon séquentielle le déroulement des traitements et de ses interactions entre  éléments du système et les acteurs
- Diagramme de communication : Représentation simplifié séquence,  avec juste échange message objets
- Diagramme Global d'intervention : Enchaîne possible entre les scénarios préalablement identifié sous forme de diagrammes de séquence
- Diagramme de temps : représentation des variation d'une donnée au cours du temps

Des dessins normalisés :
![](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/ModeleElementsUML.png/290px-ModeleElementsUML.png)
Dépendance : 
![](https://commons.wikimedia.org/wiki/File:UML_Rel_dependency.png?uselang=fr)

Agrégation : (Copie mémoire)
![](https://commons.wikimedia.org/wiki/File:UML_Rel_aggregation.jpg?uselang=fr)

Composition : (Si un est détruit, l'autre ne peut pas fonctionner)
![](https://upload.wikimedia.org/wikipedia/commons/1/12/UML_Rel_composition.jpg)









