# Architecture des vues

Le thème se trouve dans `anpaski/web/app/themes/timberrock/`. Les vues Twig sont rangées par rôle pour séparer la structure globale, les blocs de page et les contenus répétés.

## Organisation de `views`

```text
views/
├── base.twig
├── partials/       éléments communs : header, footer, menu, breadcrumb
├── helpers/        helpers Twig : images et icônes
├── cards/          cartes de contenus : service, FAQ, marque
├── sections/       blocs réutilisables d'une page
└── templates/
    ├── pages/      pages WordPress
    ├── singles/    contenus individuels
    └── archives/   listes et archives
```

### `base.twig`

`base.twig` est le layout commun. Il charge le head, la barre de réservation, le header, le breadcrumb, le contenu et le footer. Il expose notamment les classes `body_class` et `page-{slug}` et transmet à Twig le contexte Timber.

Le bandeau bleu situé avant le header reprend le lien `get_permalink_boutique()`. Il doit donc être vérifié dans chaque langue avant livraison.

### `templates/pages`

Les templates de pages correspondent aux pages WordPress : `accueil.twig`, `le-magasin.twig`, `la-station.twig`, `contact.twig`, `questions-frequentes.twig`, les pages légales et `ui-kit.twig`.

Les fichiers `blog.twig`, les archives d'articles et les cartes d'articles présents dans le socle ne font pas partie du périmètre fonctionnel du template livré. Ils peuvent être supprimés ou conservés comme éléments optionnels, mais ne doivent pas être alimentés ni annoncés comme une fonctionnalité du site sans demande spécifique.

La page d'accueil est assemblée dans `templates/pages/accueil.twig` dans cet ordre :

1. hero ;
2. marques ;
3. présentation ;
4. chiffres ;
5. services ;
6. réservation ;
7. avantages ;
8. offres ;
9. localisation ;
10. avis ;
11. FAQ.

Pour changer l'ordre ou retirer un bloc, modifier `accueil.twig`. Pour modifier le HTML ou le contenu d'un bloc, modifier le fichier correspondant dans `sections/`.

### `sections`

Les sections sont des blocs visuels complets : `hero.twig`, `services.twig`, `produits.twig`, `reservation.twig`, `offres.twig`, `localisation.twig`, `avis.twig`, `faq.twig`, `a-propos.twig`, `avantages.twig`, `chiffres.twig`, `marques.twig` et `partenaires.twig`.

Une section peut recevoir des données depuis un template de page ou directement depuis le contexte Timber. Les titres et textes génériques doivent être comparés à la maquette puis remplacés lorsqu'ils contiennent du contenu de démonstration.

### `partials`

Les partials regroupent les éléments communs :

- `header.twig` pour toute la navigation desktop et mobile ;
- `footer.twig` pour les garanties, les colonnes, les mentions légales et les réseaux sociaux ;
- `head.twig` pour les métadonnées ;
- `breadcrump.twig` pour le fil d'Ariane ;
- `menu.twig` si des éléments de navigation complémentaires sont utilisés.

### `cards` et `helpers`

Les cartes utilisées par le périmètre du template rendent les contenus répétables : `service.twig`, `faq.twig` et `marque.twig`. Les cartes `article.twig` et `post.twig` sont optionnelles tant que le site ne comprend pas de blog. Les helpers d'image et d'icône évitent de dupliquer les traitements Twig dans chaque section.

## Méthode de modification

Pour une nouvelle page, étendre `base.twig` et composer la page avec des sections. Pour un nouveau bloc répétable, créer une carte dans `cards/`. Pour une nouvelle donnée métier, vérifier d'abord si elle doit venir d'un Custom Post Type, d'un champ Carbon Fields ou d'une option globale avant de l'écrire en dur dans Twig.

Ne pas modifier directement `assets/styles/main.css` lorsque la source SCSS existe : modifier les fichiers SCSS puis compiler la feuille de style.
