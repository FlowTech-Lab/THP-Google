# Page d’accueil Google — Clone local (THP02/Google)

Une reproduction simple et soignée de la page d’accueil Google en HTML/CSS (thème sombre), pensée pour s’ouvrir localement sans dépendance externe. Le formulaire pointe vers la recherche Google réelle.

## Aperçu

- Logo local (`logo.svg`), icône de loupe (`loupe.png`).
- Barre de recherche avec libellé accessible (label masqué) et focus visibles.
- En-tête et pied de page structurés en `<nav>` pour une sémantique propre.
- Responsive de base via `meta viewport` et mise en page flexible.

## Fonctionnalités

- Recherche: soumet les requêtes vers `https://www.google.com/search` avec la méthode GET (`name="q"`).
- Boutons: "Recherche Google" et "J'ai de la chance" (comportement visuel; le second n’implémente pas la redirection spéciale, voir TODO).
- Accessibilité: label masqué via `.sr-only`, contours de focus (`:focus-visible`), structure sémantique des zones.
- Thème sombre: couleurs proches de `#202124` (Google thème sombre) pour le fond, texte contrasté, hover doux.

## Arborescence

```
THP02/Google/
├─ index.html      # Page principale
├─ style.css       # Styles (fondations, layout, composants)
├─ logo.svg        # Logo Google vectoriel local
├─ loupe.png       # Icône loupe (barre de recherche)
└─ README.md       # Ce fichier
```

## Utilisation

- Option 1: ouvrir directement `index.html` dans votre navigateur.
- Option 2 (recommandé): servir en local pour éviter certains blocages CORS/URL relatives.
  - VS Code: extension Live Server → "Open with Live Server" depuis `index.html`.
  - Node: `npx serve .` puis ouvrir l’URL indiquée.

## Détails d’implémentation

- HTML
  - Langue du document: `fr`.
  - `<header>`: navigation principale (Gmail, Images, Applications, Profil – liens à compléter selon besoin).
  - `<main>`: zone héro (logo) + formulaire de recherche (champ `name="q"`).
  - `<footer>`: 3 blocs de liens (gauche/centre/droite). Quelques URLs sont des placeholders à remplacer si vous souhaitez une fidélité totale.

- CSS
  - Reset léger: `box-sizing: border-box`, layout vertical `header/main/footer`.
  - Accessibilité: `.sr-only` pour label visuel masqué mais lu par lecteurs d’écran.
  - Styles de focus: `:focus-visible` pour naviguer confortablement au clavier.
  - Composants: centrage du logo, barre de recherche (icône loupe), boutons, navs du footer.

## Accessibilité (a11y)

- Label explicite pour le champ de recherche (masqué visuellement mais présent dans le DOM).
- Focus visible sur les liens et éléments interactifs.
- Structure sémantique: `header`, `main`, `footer`, `nav`, `form`, `label`.

## Limites connues / TODO

- "J’ai de la chance": pour reproduire le vrai comportement Google, un traitement spécifique côté Google est nécessaire; localement, le bouton agit comme un submit standard.
- Liens d’en-tête et de footer: certains sont actuellement des placeholders (`#`). Remplacez par les URLs officielles si souhaité.
- Thème clair: le projet est en thème sombre. Un toggle sombre/clair peut être ajouté.
- Icônes supplémentaires: l’icône d’"Applications" et l’avatar sont simplifiés; on peut intégrer un SVG inline plus fidèle.

## Technologies

- HTML5 sémantique
- CSS3 (flexbox, media queries, focus-visible)

## Personnalisation rapide

- Modifier les couleurs dans `style.css` (variables possibles si vous souhaitez factoriser).
- Adapter les liens dans `index.html` (header/footer) vers les services Google réels.
- Remplacer `logo.svg`/`loupe.png` par vos propres assets si besoin.

## Crédits

- Logo et marque Google appartiennent à Google LLC. Projet réalisé à des fins pédagogiques.

---

Besoin d’un réglage pixel-perfect (espacements/typographies identiques à google.com), d’un thème clair, ou d’ouvrir tous les liens dans de nouveaux onglets (`target="_blank"`) ? Ouvrez une issue/PR ou demandez-moi d’ajuster.
