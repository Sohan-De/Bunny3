# Snack La Gamba Royale · Template 5

Site vitrine statique pour le Snack La Gamba Royale, 25 bis avenue Maréchal Joffre, 34500 Béziers.
HTML5, CSS3 et JavaScript vanilla. Aucun framework, aucun build, aucune dépendance, aucune requête externe à l'exécution.

Direction artistique : marché et port. Fond papier froid, bleu mer, sable doré, et une ardoise de menu en bois. Coins carrés, filets noirs épais, pas d'ombre. Bandes d'auvent rayées sous l'en-tête et en bas de page. Titres en Syne, texte en Public Sans.

## Structure

```
template-5/
├── index.html
├── mentions-legales.html
├── README.md
└── assets/
    ├── css/styles.css
    ├── js/main.js
    ├── img/
    │   ├── favicon.svg          (fourni)
    │   ├── logo-mark.svg        (fourni)
    │   ├── poisson.jpg          (à ajouter, carré)
    │   ├── gallery-1.jpg        (à ajouter, 4:3)
    │   ├── gallery-2.jpg        (à ajouter, carré)
    │   ├── gallery-3.jpg        (à ajouter, carré)
    │   └── map.jpg              (à ajouter)
    └── fonts/
        ├── syne-latin-wght-normal.woff2              (à ajouter)
        └── public-sans-latin-wght-normal.woff2       (à ajouter)
```

## Données déjà renseignées

Source : fiche Google Business (4,9 sur 39 avis, €10–20, « Fast food restaurant »).

- Nom, adresse, téléphone : +33 7 74 21 27 40.
- Services : sur place, à emporter, livraison sans contact.
- Mise en avant sur la fiche : poisson frais, poisson grillé, frites maison.
- Concept : poissonnerie et restaurant. Le client choisit son poisson, il est pesé puis grillé. Décrit dans les avis, présenté dans la section « Vous choisissez, on grille ».
- Avis : 3 avis avec initiales et dates approximatives, textes repris de la fiche. Le troisième est « Top. », c'est tout ce qui était visible.
- **Pas de site web** : le lien de la fiche est cassé. Aucun lien vers un site n'apparaît sur le site.

## Ce qui manque

**Horaires** : la fiche affiche « Add hours », donc aucun horaire. Le statut affiche « Horaires à compléter » tant que les attributs `data-open` et `data-close` ne sont pas remplis dans `index.html`.

**Carte et prix** : seuls « poisson grillé », « pêche du jour », « Pisces », et « frites maison » sont cités. Les prix sont en placeholders. Un avis indique 13 € les 500 g pour le poisson au poids, à confirmer avant d'afficher un prix.

## Placeholders à remplacer

Chaque valeur manquante est en jaune (`.lg-placeholder`). Recherchez `[` dans les fichiers.

**`index.html`**

| Élément | Action |
|---|---|
| Slogan (hero) | `[SLOGAN À COMPLÉTER]` |
| Ardoise « Au tableau » | Prix de chaque plat |
| Tableau (onglets) | Descriptions, prix et noms des plats, accompagnements, boissons, desserts. Le bandeau « CARTE INDICATIVE » est à supprimer une fois la carte réelle en place |
| Prix au poids (section poisson) | `[PRIX AU POIDS DU JOUR, À CONFIRMER]` |
| Horaires | Remplir `data-open`, `data-close` (et `data-open-2`, `data-close-2` pour une deuxième plage) sur chaque `<li data-day>` |
| Métadonnées | `[URL DU SITE]` dans `og:url` |

**`mentions-legales.html`** : toutes les valeurs à compléter sont des `<span class="lg-placeholder">` (forme juridique, SIRET, TVA, directeur de publication, hébergeur, développeur, crédits photos, e-mail RGPD, date).

Le JSON-LD `Restaurant` contient le nom, l'adresse, le téléphone, la gamme de prix et la cuisine. `aggregateRating` est absent : Google demande que la note structurée corresponde aux avis visibles, à ajouter une fois la liste complète en place.

## Images à ajouter

| Fichier | Taille recommandée | Usage |
|---|---|---|
| `poisson.jpg` | 1000 × 1000 px | Poisson au comptoir |
| `gallery-1.jpg` | 1200 × 900 px (4:3) | Comptoir |
| `gallery-2.jpg` | 900 × 900 px | Poisson sur le gril |
| `gallery-3.jpg` | 900 × 900 px | Vue du quartier |
| `map.jpg` | 960 × 720 px | Capture statique de la carte (sans iframe) |

Moins de 200 Ko par photo (JPEG, qualité 75 à 80). Le navigateur affiche des erreurs 404 dans la console tant que les images ne sont pas ajoutées.

## Polices à télécharger

Les deux polices sont sous licence SIL Open Font License (OFL).

1. **Syne** (titres) : [fonts.google.com/specimen/Syne](https://fonts.google.com/specimen/Syne). Télécharger le WOFF2 du sous-ensemble `latin`, axe de graisse variable. Renommer en `syne-latin-wght-normal.woff2`.
2. **Public Sans** (texte) : [fonts.google.com/specimen/Public+Sans](https://fonts.google.com/specimen/Public+Sans). Télécharger le WOFF2 `latin`, axe de graisse variable. Renommer en `public-sans-latin-wght-normal.woff2`.

Les deux fichiers vont dans `assets/fonts/`. Sans eux, le site utilise Arial et Helvetica.

## Aperçu local

- Double-cliquer sur `index.html`.
- Ou depuis ce dossier : `npx serve`.

## Checklist avant mise en ligne

- [ ] Saisir les horaires jour par jour et vérifier le statut
- [ ] Remplacer la carte indicative par la carte réelle avec les prix
- [ ] Confirmer le prix au poids du poisson
- [ ] Ajouter les photos dans les tailles indiquées
- [ ] Compléter les mentions légales : SIRET, forme juridique, directeur de publication, hébergeur
- [ ] Vérifier les avis sur la fiche Google et ajouter le lien quand la fiche est réparée
- [ ] Tester sur un vrai téléphone, en mode portrait et paysage
- [ ] Vérifier qu'aucune erreur 404 n'apparaît dans la console (polices et images)
