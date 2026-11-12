# mergify-config

Configuration Mergify partagée pour les dépôts de l'organisation **Tradoooo**.

## Utilisation

Ajouter à la racine d'un dépôt cible un fichier `.mergify.yml` contenant uniquement :

```yaml
extends: mergify-config
```

Le dépôt source (`mergify-config`) doit être au moins aussi visible que le dépôt cible.
Il est public, donc il peut servir aussi bien les dépôts publics que privés.

## Prérequis

- L'app GitHub Mergify doit être installée sur ce dépôt **et** sur le dépôt cible.
- Les produits **Merge Queue** et **Merge Protections** doivent être activés sur le dépôt cible
  (l'auto-merge en dépend).
- Les checks `ci` et `ci-budget` doivent exister dans la CI du dépôt cible.

## Contenu

La configuration commune :

- met en file les PR vertes sur `main` ou `master` ;
- exige `ci` et `ci-budget` ;
- merge en squash par lots de 3, avec mise à jour par merge de la base ;
- laisse le label `hold` sortir une PR de la file ;
- active l'auto-merge via les Merge Protections.
