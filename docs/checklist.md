# Checklist de livraison

## Base et identité

- [ ] La base de données est vierge et ne contient aucun contenu, réglage ou formulaire d'un ancien projet.
- [ ] Les anciens noms, domaines, téléphones, adresses, réseaux sociaux et URLs ont été recherchés dans la base, les options, les traductions et les fichiers Twig.
- [ ] Le nom du site, le logo desktop, le logo mobile, le favicon et les métadonnées sont ceux du nouveau projet.
- [ ] Les images de hero, boutique, station, offres, marques et paiements sont remplacées.

## Charte graphique

- [ ] Les couleurs primaires, secondaires et les éventuelles variables de gradient correspondent à la maquette.
- [ ] Les polices `$ff`, `$ff2` et `.cta` correspondent à la charte.
- [ ] Les titres, boutons, cartes, header et footer ont été contrôlés dans le UI kit sur desktop et mobile.
- [ ] `main.css` a été recompilé après les modifications SCSS.

## Textes et maquette

- [ ] Les labels du header, du menu mobile et du footer correspondent à la maquette.
- [ ] Les textes de boutons et leurs destinations sont corrects.
- [ ] Les titres, surtitres et sous-titres présents dans les appels `__()` correspondent à la maquette.
- [ ] Aucun `Lorem ipsum`, `LOREM`, `Offerta LOREM` ou `Stazione di LOREM IPSUM` ne reste dans les vues ou le BO.
- [ ] Les attributs `alt`, les textes d'accessibilité et les messages de réservation sont adaptés.

## Back-office et traductions

- [ ] Polylang est configuré avant la saisie des contenus.
- [ ] Les pages, services, FAQ, marques, avis, équipements et champs éditoriaux sont traduits dans chaque langue.
- [ ] Aucun blog ni contenu de type article n'est créé ou annoncé dans le périmètre du template livré.
- [ ] Le catalogue `timberrock` est à jour dans Loco Translate.
- [ ] Chaque formulaire Gravity Forms existe dans toutes les langues actives.
- [ ] Chaque formulaire Gravity Forms possède la bonne langue associée.
- [ ] Chaque formulaire traduit possède l'ID du formulaire parent de la langue par défaut, par exemple `1` si le premier formulaire de base porte l'ID `1`.
- [ ] Les libellés, choix, validations, boutons, confirmations et notifications Gravity Forms sont traduits.
- [ ] Le téléphone, l'e-mail, l'adresse, les coordonnées Google Maps et les réseaux sociaux sont renseignés et testés.
- [ ] Une URL boutique `var_site_boutique_{lang}` est renseignée pour chaque langue active.
- [ ] Les dates de saison ont été renseignées uniquement si une logique de saison dédiée a été ajoutée au projet.

## Navigation et recette

- [ ] Les slugs `le-magasin`, `la-station`, `contact` et `questions-frequentes` existent ou ont été adaptés dans les templates.
- [ ] Le menu services affiche les bons services et le bon nombre d'éléments.
- [ ] Le menu desktop, le menu mobile, le sélecteur de langue et le footer fonctionnent.
- [ ] Les liens boutique fonctionnent dans le bandeau, le header, les offres et le footer.
- [ ] Le site a été testé sur desktop et mobile, dans chaque langue.
- [ ] Une recherche finale des anciens noms, domaines, `Lorem ipsum` et URLs d'anciens projets ne retourne aucun résultat.
