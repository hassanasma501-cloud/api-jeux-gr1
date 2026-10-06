# 1. Fusionner les pull requests par squash

- **Date** : 2026-10-06
- **Statut** : Acceptée

## Contexte

Notre équipe travaille avec une issue par changement, une branche dédiée et une pull request relue avant fusion dans `main`.

Nous devons choisir une stratégie de fusion commune afin de garder un historique Git lisible et cohérent.

## Options envisagées

### 1. Merge commit

**Pour :**
- conserve tous les commits de la branche ;
- garde l’historique complet du développement.

**Contre :**
- ajoute un commit de fusion supplémentaire ;
- les commits intermédiaires comme `wip` ou les petites corrections restent visibles sur `main` ;
- l’historique devient plus difficile à lire.

### 2. Squash and merge

**Pour :**
- regroupe tous les commits d’une pull request en un seul commit sur `main` ;
- garde un historique plus clair ;
- une pull request correspond à un changement identifiable.

**Contre :**
- le détail des commits de travail disparaît de l’historique de `main`.

### 3. Rebase and merge

**Pour :**
- conserve les commits sans créer de commit de fusion ;
- produit un historique linéaire.

**Contre :**
- demande que les commits soient déjà propres et bien organisés ;
- peut rendre l’historique plus difficile à comprendre si une pull request contient beaucoup de petits commits.

## Décision

Nous choisissons **Squash and merge**.

Cette méthode permet de conserver un historique de `main` lisible, avec un seul commit par pull request relue.

## Conséquences

- **Positif :** l’historique de `main` est plus clair et chaque commit correspond à un changement validé par une pull request.
- **Négatif :** le détail des différents commits réalisés pendant le développement n’apparaît plus directement dans l’historique de `main`.
- **À revoir si :** nous avons besoin de conserver individuellement les commits d’une pull request pour comprendre ou retracer précisément certaines modifications.