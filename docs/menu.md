# Header et menu

Le menu principal est construit directement dans `anpaski/web/app/themes/timberrock/views/partials/header.twig`. Il ne repose pas sur un menu WordPress classique.

## Navigation desktop

Le header desktop est séparé en deux zones :

- `.header-menu` : logo, services, informations et station ;
- `.header-contact` : téléphone, contact, sélecteur de langue et bouton de réservation.

Le lien **Services** ouvre un menu déroulant. Les services sont récupérés par `app.getPostType('service', 3, 'ASC')`, donc le header affiche au maximum trois services, classés par date croissante selon le comportement de la requête.

Les autres liens utilisent des slugs de pages : `le-magasin`, `la-station` et `contact`. Si un slug change dans WordPress, le lien Twig doit être adapté en même temps.

## Navigation mobile

Lorsque `is_mobile()` est vrai, le header affiche :

- un bouton burger piloté par le contrôleur Stimulus `mobile-menu` ;
- le logo mobile ;
- le bouton `Prenota online` ;
- un menu mobile avec les services, les pages principales, le téléphone, le contact et les langues.

Le desktop et le mobile partagent donc les mêmes labels, mais leurs contrôles et leur structure HTML sont distincts. Toute modification du menu doit être testée dans les deux affichages.

## Réservation et langue

Le bouton de réservation appelle `get_permalink_boutique()`. La fonction choisit l'URL Carbon Fields correspondant à la langue active avec la clé `var_site_boutique_{lang}`. Si l'URL de la langue courante est vide, le code utilise l'URL de la langue par défaut.

**Exemple :** pour le français et l'anglais, les options attendues sont `var_site_boutique_fr` et `var_site_boutique_en`. Un bouton affiché en anglais doit ouvrir l'URL anglaise si elle est renseignée.

Le sélecteur de langue utilise Polylang et affiche les slugs de langue. Vérifier qu'il est présent et fonctionnel dans le header desktop, le menu mobile et le footer.

## Éléments à personnaliser

Contrôler dans la maquette puis adapter :

- les labels `Servizi`, `Informazioni`, `La stazione`, `Contattaci` et `Prenota online` ;
- les titres du menu services ;
- le logo desktop et mobile ;
- le téléphone et le lien de contact ;
- les slugs des pages ;
- le libellé et la destination de la réservation ;
- les traductions dans chaque langue.

Le menu utilise actuellement principalement des textes italiens. Ces chaînes portent le text domain `timberrock` et doivent être traduites avec Loco Translate ou remplacées selon la langue source du nouveau site.
