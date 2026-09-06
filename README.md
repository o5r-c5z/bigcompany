# bigcompany

Feuille de style personnalisée du site Squarespace de **Big Company**
(<https://www.bigcompany.fr>), telle qu'elle était en 2016. Le fichier
`styles.less` était collé dans le panneau « Custom CSS » de Squarespace : il
redéfinit la navigation, la typographie, la grille de galerie du portfolio, le
bouton « Demoreel », les formulaires et le pied de page du template.

**Année de réalisation / livraison : 2016.**
Les polices et images référencées dans `styles.less` ont été mises en ligne sur
les assets Squarespace du site les 28 et 29 novembre 2016 (timestamps des URLs).
Le premier commit git (2026-09-06) correspond à l'archivage du fichier.

> **Cette feuille de styles correspond à une version antérieure du site, aujourd'hui
> remplacée.**

## Contenu

- `styles.less` — feuille de style unique (syntaxe LESS ; extension `.css`
  d'origine, le panneau Squarespace étant intitulé « Custom CSS »). Contient :
  - deux `@font-face` pour la police `Gotham` (Book 400, Bold 700), chargée
    depuis les assets Squarespace du site ;
  - la barre de navigation mobile (`#sidecarNav`, `#titres`,
    `.mobile-nav-open`) et la navigation principale (`#mainNavigation`) ;
  - une grille de galerie sur-mesure pour le portfolio, en 4 et 5 vignettes par
    ligne (`.sqs-gallery-block-grid…thumbnails-per-row-4` / `-5`), avec
    survol : titre en incrustation et voile rouge `rgba(217,18,18,0.5)` ;
  - le bouton « Demoreel » (`.desc-wrapper:last-of-type`) et les boutons
    Squarespace (`.sqs-block-button-element`, `.sqs-system-button`) ;
  - les champs de formulaire (`.form-wrapper .field-list`), avec une flèche
    personnalisée pour les `<select>` ;
  - le pied de page (`#footer`), filet horizontal et logo.

## Stack technique

- Personnalisation d'un site **Squarespace**. Le template Squarespace lui-même
  n'est pas dans le repo ; ce fichier ne fonctionne qu'injecté dans ce site.
- Syntaxe **LESS** (règles imbriquées, sélecteur parent `&`) telle que
  supportée par l'éditeur CSS de Squarespace, qui compile la feuille. Le
  fichier n'est donc pas du CSS valide en l'état.
- Police **Gotham** (Book, Bold) servie via `@font-face` depuis
  `static1.squarespace.com/static/583411bd725e25d98aacd19f/…`.
- Sélecteurs ciblant les composants Squarespace : `#sidecarNav`,
  `#mainNavigation`, `.sqs-gallery-*`, `.form-wrapper`, `.sqs-block-*`,
  `#footer`.
- Préfixes vendeurs (`-webkit-`, `-moz-`, `-ms-`, `-o-`) sur les transitions et
  transforms, écrits à la main.
- Aucun gestionnaire de dépendances, aucun bundler, aucun build local.

## Développement

Prérequis : un accès à l'administration du site Squarespace.

Il n'y a pas de build local. Le circuit est :

```sh
# éditer la feuille
$EDITOR styles.less

# puis, dans Squarespace : Design → Custom CSS
# coller l'intégralité de styles.less et enregistrer
```

Notes de configuration :

- Les URLs sont absolues et pointent vers les assets du site Squarespace
  d'identifiant `583411bd725e25d98aacd19f` : les deux fichiers `Gotham-*.otf`
  et l'image `bande8.png` (flèche des `<select>`). En cas de changement de
  site, réuploader ces fichiers et remplacer les URLs.
- La couleur d'accent (voile de survol des vignettes) est
  `rgba(217,18,18,0.5)`.
- La grille de galerie suppose un bloc *Grid* Squarespace réglé sur 4 ou 5
  vignettes par ligne ; les autres réglages ne sont pas pris en charge.

## Crédits

- **Conception et intégration CSS** — Olivier Charvoz
- **Commanditaire** — Big Company (<https://www.bigcompany.fr>)

Copyright © 2016 Big Company. Tous droits réservés.
