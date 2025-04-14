# Automate - Implémentation d'automates finis en Python

## Description
Ce projet est une implémentation complète d'automates finis en Python, développé dans le cadre du cours "Mathématiques discrètes" (LU2IN005) à Sorbonne Université. Il fournit une bibliothèque permettant de créer, manipuler et opérer sur des automates finis, structures fondamentales en théorie des langages et en informatique théorique.

## Fonctionnalités

- **Création d'automates** de différentes manières :
  - À partir d'un ensemble de transitions
  - À partir d'ensembles d'états et de transitions
  - À partir d'un fichier de description

- **Opérations sur les automates** :
  - Test d'acceptation d'un mot
  - Déterminisation d'automates
  - Complétion d'automates
  - Opérations ensemblistes : union, intersection, complémentaire
  - Opérations rationnelles : concaténation, étoile de Kleene

- **Manipulation** :
  - Ajout/suppression d'états et de transitions
  - Visualisation graphique des automates
  - Transformation d'automates (préfixage d'états, etc.)

## Structure du projet

Le projet est organisé selon une architecture orientée objet avec plusieurs classes principales :
- `State` : représente un état d'un automate avec son identifiant, son statut (initial/final) et son étiquette
- `Transition` : représente une transition entre deux états avec une étiquette
- `Automate` : la classe principale qui encapsule les ensembles d'états et de transitions et fournit les opérations sur les automates

## Exemples d'utilisation

### Création d'un automate

```python
# Création des états
s0 = State(0, True, False)  # État 0, initial, non final
s1 = State(1, False, False) # État 1, non initial, non final
s2 = State(2, False, True)  # État 2, non initial, final

# Création des transitions
t1 = Transition(s0, "a", s0)
t2 = Transition(s0, "b", s1)
t3 = Transition(s1, "a", s2)
t4 = Transition(s1, "b", s2)
t5 = Transition(s2, "a", s0)
t6 = Transition(s2, "b", s1)

# Création de l'automate
auto = Automate({t1, t2, t3, t4, t5, t6})

# Affichage
print(auto)
auto.show()
```

### Chargement d'un automate depuis un fichier

```python
automate = Automate.creationAutomate("chemin/vers/fichier.txt")
```

Format du fichier :
```
#E: 0 1 2  # États
#I: 0       # États initiaux
#F: 2       # États finaux
#T: (0 a 0) # Transitions (source lettre destination)
    (0 b 1)
    (1 a 2)
    ...
```

## Installation et prérequis

Ce projet utilise Python 3 et nécessite les bibliothèques suivantes :
- graphviz (pour la visualisation)

Aucune installation spécifique n'est nécessaire au-delà de Python et des dépendances. Le projet peut être exécuté directement à partir du notebook Jupyter fourni.

## Auteur

- Yoan LE NEVEZ

## Licence

Ce projet a été développé dans un cadre académique à Sorbonne Université. Tous les droits sont réservés.

## Contexte académique

Ce projet a été réalisé dans le cadre du cours "Mathématiques discrètes" (LU2IN005) à Sorbonne Université pour l'année 2023-2024. L'objectif était d'implémenter en Python les concepts fondamentaux des automates finis vus en cours et en TD. 