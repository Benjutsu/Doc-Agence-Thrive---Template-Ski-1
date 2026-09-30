# Personnalisation

La personnalisation d'un site basé sur Anpaski se fait à trois niveaux : la charte SCSS, les textes et templates Twig, puis les données du back-office.

## Commencer par une base vierge

Installer le nouveau site sur une base de données vierge. Une ancienne base peut conserver des pages, médias, options Carbon Fields, traductions Polylang, URLs boutique, coordonnées, formulaires Gravity Forms et termes de contenus d'un autre projet.

Après installation, rechercher les anciens noms de station, société, domaines, téléphones, adresses et réseaux sociaux dans la base, les options du thème, les médias, les traductions et les fichiers Twig. Modifier uniquement le nom du site dans WordPress ne suffit pas.

**Exemple :** pour un site « Mont-Blanc Ski », aucune occurrence de `Cinto`, `Anpaski`, ancien domaine ou ancienne URL de réservation ne doit rester dans le header, le footer, les métadonnées, les options ou les formulaires.

## Langue source du code

Les chaînes visibles du thème sont principalement écrites en italien : `Servizi`, `Informazioni`, `La stazione`, `Prenota online`, `Contattaci`, `Pagamento sicuro` et plusieurs titres de sections. Certaines chaînes techniques ou administratives sont en français ou en anglais.

Les chaînes front sont généralement enveloppées dans `__()` ou `_e()` avec le text domain `timberrock`. Elles doivent être considérées comme des textes sources à traduire, pas comme le contenu final du projet. Après toute modification d'une chaîne Twig, mettre à jour le catalogue dans Loco Translate et vérifier le résultat dans chaque langue.

Ne pas traduire les slugs, les clés PHP, les noms de champs comme `var_site_tel` ou les valeurs techniques utilisées par le code.

## Couleurs SCSS

Le fichier `assets/styles/abstracts/_var.scss` centralise les couleurs du template. Les variables principales actuelles sont :

```scss
$dark: #0F223D;
$secondary-1: #42A5F5;
$secondary-2: #2377A6;
$secondary-3: #F1F2F6;
```

Dans ce template, `$dark` joue le rôle de couleur primaire et `$secondary-1` de couleur secondaire. `$secondary-2` sert notamment aux variantes et `$secondary-3` aux fonds et bordures claires. Le template ne définit pas actuellement de variable `$gradient-color` dédiée : si la maquette utilise un dégradé, ajouter une variable source dans `_var.scss`, puis l'utiliser dans les composants concernés plutôt que de répéter des valeurs hexadécimales.

**Exemple :** pour une charte rouge et bleu nuit, remplacer `$dark` par le bleu nuit des textes, `$secondary-1` par le rouge des CTA et `$secondary-2` par sa variante foncée. Vérifier les contrastes avant de compiler `main.css`.

## Typographies dans `_ui.scss`

Le fichier `assets/styles/pages/_ui.scss` définit les styles du UI kit et des classes de texte :

- `$ff`, actuellement `Oswald`, est utilisé pour les titres `.h1`, `.h2` et `.h3` ;
- `$ff2`, actuellement `DM Sans`, est utilisé pour les textes `.body-large` et `.body-small` ;
- `.cta` utilise actuellement `Rubik`.

Pour adapter la typographie : charger les polices retenues, modifier les variables dans `_var.scss`, ajuster les tailles, graisses, interlignes et capitales dans `_ui.scss`, puis contrôler `ui-kit`, hero, boutons, cartes et footer sur desktop et mobile.

## Textes Twig et maquette

Comparer tous les textes codés dans les appels `__()` avec la maquette. Remplacer les contenus de démonstration présents notamment dans `hero.twig`, `a-propos.twig`, `avantages-gris.twig`, `avis.twig`, `chiffres.twig`, `offres.twig`, `la-station.twig`, `le-magasin.twig` et `contact.twig`.

Rechercher `Lorem ipsum`, `LOREM`, `Offerta LOREM`, `Stazione di LOREM IPSUM` et les textes génériques. Vérifier également les textes qui ne sont pas des Lorem ipsum mais qui sont déjà métier : titres de sections, surtitres, descriptions et attributs `alt`.

## Contrôle des textes visibles

### Header et footer

Comparer les labels du header, du menu mobile et du footer à la maquette : services, informations, station, contact, réservation, garanties, moyens de paiement, mentions légales, coordonnées et réseaux sociaux. Le footer contient encore un exemple `Stazione di LOREM IPSUM` et un `alt="Lorem ipsum"` qui doivent obligatoirement être remplacés.

### Boutons

Vérifier les libellés et les destinations de `Prenota online`, `Prenota ora`, `Contattaci`, `Mostra sulla mappa`, `Consultare` et `Per saperne di più...`. Contrôler la casse, la traduction, la longueur du texte dans le bouton et l'action réelle du lien.

### Titres et sous-titres

Les titres présents dans `__()` doivent correspondre à la maquette dans chaque langue. Contrôler les titres de hero, les surtitres de sections, les titres de services, offres, FAQ, station, boutique, contact, avis et chiffres. Un texte déjà présent dans le code n'est pas nécessairement définitif.

## Personnalisation du back-office

### Identité

- renseigner le nom du site dans WordPress et les champs SEO ;
- remplacer les logos `template-logo.png` et `template-logo-mobile.png` ;
- vérifier le favicon, les images de partage et les attributs `alt` ;
- remplacer les visuels de hero, boutique, station, offres, marques et paiements.

### Coordonnées, boutique et réseaux

Dans les options Carbon Fields **Coordonnées**, renseigner le téléphone, l'e-mail, l'adresse, les coordonnées et le lien Google Maps. Dans **Réseaux sociaux**, renseigner Facebook, Instagram et X/Twitter.

Dans l'onglet **Boutique**, renseigner une URL `var_site_boutique_{lang}` pour chaque langue Polylang active. Par exemple : `var_site_boutique_fr` et `var_site_boutique_en`.

Tester les liens depuis le bandeau bleu, le header desktop, le header mobile, les offres, le footer et les éventuels boutons de réservation.

### Saisons

Le thème Anpaski ne contient pas de calcul automatique de saison comparable à Cortina. Les deux saisons ne sont donc pas des valeurs globales utilisées par `StarterSite` dans l'état actuel du template. Si le futur site doit afficher des contenus ou URLs différents selon l'hiver et l'été, il faut ajouter et documenter une logique dédiée avant de demander la saisie de dates dans le BO.

## Traductions

Configurer les langues Polylang avant de saisir les contenus. Traduire les pages, services, FAQ, marques, avis, équipements, champs éditoriaux et chaînes du thème avec Loco Translate dans le domaine `timberrock`. Aucun contenu de blog ou article n'est à créer pour le périmètre actuel du template.

### Gravity Forms

Chaque formulaire doit exister dans toutes les langues actives. Dans les réglages de chaque formulaire, renseigner :

- la langue associée au formulaire ;
- l'ID du formulaire parent correspondant au formulaire de la langue par défaut ;
- les libellés, choix, validations, boutons, confirmations et notifications traduits.

**Exemple :** si le formulaire français de base est le premier créé et possède l'ID `1`, le formulaire anglais peut avoir l'ID `2`, la langue `en` et le formulaire parent `1`. Le formulaire italien peut avoir l'ID `3`, la langue `it` et le même parent `1`.

Un formulaire traduit visuellement mais relié au mauvais parent peut être absent du bon parcours ou associé à une mauvaise langue.
