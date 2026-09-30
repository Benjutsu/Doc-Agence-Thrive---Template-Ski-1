# Template ski 1 - Anpaski

> **Référence GitLab** : le template 1 se trouve sur la branche `starter` du dépôt [AgenceThrive/anpaski](https://gitlab.com/AgenceThrive/anpaski/-/tree/starter).
> **Base fonctionnelle** : le template 1 est basé sur **Cinto Sport**, qui constitue la version la plus évoluée du socle Anpaski.

## Présentation

Le template 1 est basé sur le projet **Anpaski**, dont la version de référence est **Cinto Sport**, la version la plus évoluée du socle. Il propose une base WordPress réutilisable pour les magasins de ski, les loueurs de matériel et les stations de montagne.

Anpaski a été standardisé pour conserver les éléments qui se répètent d'un site à l'autre :

- une architecture Bedrock, Timber et Twig ;
- un header responsive avec menu services, navigation desktop et navigation mobile ;
- des sections de page réutilisables pour les services, les produits, les offres, la station et la réservation ;
- des Custom Post Types pour les services, FAQ, marques, avis et équipements ;
- un système de champs Carbon Fields et de contexte Timber ;
- une gestion multilingue avec Polylang et Loco Translate ;
- une intégration Gravity Forms avec association entre formulaires traduits et formulaire parent.

Cette standardisation permet de lancer plus rapidement les futurs sites, de limiter les développements spécifiques et de garder une cohérence technique. Le contenu, l'identité visuelle et les textes doivent toutefois être remplacés pour chaque nouveau projet.

## Périmètre du template

Le template couvre notamment :

- une page d'accueil composée de sections éditoriales ;
- un accès aux services depuis le header ;
- une page boutique, une page station, une page contact et une FAQ ;
- des cartes de services, FAQ et marques ;
- des liens de réservation vers une boutique externe par langue ;
- des pages légales et un UI kit de contrôle.

La documentation détaille l'organisation des vues, le header, les adaptations SCSS/Twig, la personnalisation du BO et la recette.

Voir également :

- [Architecture des vues](architecture.md)
- [Header et menu](menu.md)
- [Personnalisation](personnalisation.md)
- [Checklist de livraison](checklist.md)

**À retenir :** la checklist doit être parcourue avant toute mise en ligne. Les pages de documentation doivent être consultées dans l'ordre adapté au projet.
