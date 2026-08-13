# Nina Carducci — Site web optimisé

Projet d’audit, de débogage et d’optimisation du site web de **Nina Carducci**, photographe professionnelle spécialisée dans les mariages, portraits et événements.

L’objectif de cette intervention était d’améliorer la qualité globale du site en travaillant sur quatre axes principaux :

* **Performance**
* **SEO**
* **Accessibilité**
* **Correction des bugs fonctionnels**

L’audit initial et la validation des améliorations ont notamment été réalisés avec **Google Lighthouse**, **Chrome DevTools** et **WAVE**.

## Présentation du projet

Le site présente l’activité de Nina Carducci à travers différentes sections :

* une galerie photographique ;
* une présentation de la photographe ;
* les services proposés ;
* un formulaire de contact ;
* une navigation principale ;
* des liens vers les réseaux sociaux.

Le projet initial comportait plusieurs problèmes techniques et d’optimisation qui dégradaient les performances, l’accessibilité et la visibilité du site.

Le site final conserve sa structure visuelle tout en améliorant considérablement sa qualité technique. Le document HTML final intègre notamment une meta description, des ressources JavaScript différées, le préchargement de l’image principale, des données structurées et des métadonnées Open Graph.

## Audit initial

L’analyse initiale réalisée avec Lighthouse a permis d’identifier plusieurs problèmes :

* images trop lourdes ;
* ressources bloquantes ;
* structure HTML insuffisamment sémantique ;
* bugs dans la galerie ;
* absence de données structurées ;
* hiérarchie des titres perfectible ;
* attributs `alt` manquants ou insuffisants.

Les premiers scores Lighthouse mettaient en évidence une marge d’amélioration importante, notamment en performance, accessibilité et SEO.

## Corrections des bugs

Deux bugs fonctionnels principaux ont été corrigés.

### Navigation dans la galerie

Les flèches de navigation de la modale ne permettaient pas correctement de passer à l’image suivante ou précédente.

L’analyse du JavaScript avec **Chrome DevTools** et l’utilisation de **breakpoints** ont permis d'identifier une erreur dans la gestion de l’index représentant l’image active.

La logique a été corrigée afin que l’index soit correctement mis à jour lors des interactions avec les flèches.

### Filtre actif

Le second problème concernait l’état visuel du filtre sélectionné.

La logique JavaScript a été corrigée afin que le bouton actif soit correctement identifié et mis en évidence dans l’interface.

## Optimisations de performance

### Conversion des images

Les images représentaient une part importante du poids de la page.

Elles ont été :

* converties au format **WebP** ;
* compressées ;
* optimisées afin de réduire leur poids ;
* utilisées avec des dimensions adaptées.

L’objectif était notamment de réduire significativement le poids global de la page et d’améliorer les temps de chargement.

### Lazy Loading

Le **lazy loading** a été mis en place sur les images secondaires.

Avant optimisation, les images étaient chargées immédiatement.

Après optimisation, les images secondaires sont chargées lorsqu’elles deviennent nécessaires, ce qui permet de limiter les ressources consommées au chargement initial.

### Optimisation du LCP

L’image principale a été priorisée afin d'améliorer le **Largest Contentful Paint (LCP)**.

Le document final utilise notamment :

```html
<link
    rel="preload"
    as="image"
    href="./assets/images/slider/ryoji-iwata-wUZjnOv7t0g-unsplash.webp">
```

### Chargement différé du JavaScript

Les scripts JavaScript ont été chargés avec l’attribut `defer` afin de ne pas bloquer inutilement l’analyse et le rendu initial du document.

Le HTML final applique notamment `defer` aux scripts Bootstrap, à `maugallery.js` et à `scripts.js`.

## Optimisations SEO

### Balise `title`

Une balise `title` pertinente a été ajoutée :

```html
<title>Nina Carducci Photographe</title>
```

### Meta description

Une description destinée aux moteurs de recherche a été ajoutée :

```html
<meta
    name="description"
    content="Photographe professionnelle spécialisée en mariages, portraits et événements à Bordeaux et déplacements possibles en Île-de-France">
```

### Structure sémantique

La structure HTML a été améliorée afin d'utiliser davantage de balises sémantiques telles que :

* `header`
* `main`
* `section`
* `nav`
* `footer`

La hiérarchie des titres a également été restructurée pour suivre un ordre logique `H1 → H2 → H3`.

### Données structurées

Un balisage **Schema.org / JSON-LD** de type `LocalBusiness` a été ajouté afin de fournir aux moteurs de recherche des informations structurées sur l’activité de Nina Carducci.

Le balisage contient notamment le nom, l’adresse, le téléphone, les horaires, l’URL et la description de l’activité.

Cette optimisation vise notamment à améliorer la compréhension du site par les moteurs de recherche et sa visibilité locale.

## Accessibilité

Plusieurs améliorations ont été apportées afin de rendre le site plus accessible.

### Attributs `alt`

Les images ont reçu des textes alternatifs plus descriptifs afin d’améliorer leur compréhension par les lecteurs d’écran.

Le HTML final contient notamment des descriptions détaillées pour les images du carrousel et le lien Instagram.

### Formulaire

Les labels ont été correctement associés aux champs du formulaire afin d’améliorer la navigation au clavier et l'utilisation par les technologies d’assistance.

### Structure sémantique

L’utilisation de balises HTML sémantiques améliore également la compréhension du contenu par les outils d’assistance.

### Attributs ARIA

Des attributs **ARIA** ont été ajoutés pour améliorer l’accessibilité de certains éléments interactifs.

Une analyse complémentaire a été effectuée avec **WAVE**. Aucun problème critique n’a été détecté ; quelques améliorations de contraste restent néanmoins possibles.

## Réseaux sociaux

Des métadonnées **Open Graph** ont été ajoutées afin d’optimiser l’aperçu du site lors de son partage sur les réseaux sociaux.

Le document final contient notamment :

```html
<meta property="og:title" ...>
<meta property="og:description" ...>
<meta property="og:image" ...>
<meta property="og:url" ...>
<meta property="og:type" content="website">
```

Les Twitter Cards n’ont volontairement pas été ajoutées, le projet ne disposant pas d’une présence identifiée sur Twitter. Open Graph a donc été privilégié.

## Technologies et outils

### Technologies

* **HTML5**
* **CSS3**
* **JavaScript**
* **jQuery**
* **Bootstrap**
* **JSON-LD / Schema.org**

Le projet utilise notamment Bootstrap et jQuery côté front-end, ainsi que plusieurs scripts JavaScript dédiés à la galerie.

### Outils d'audit et de développement

* **Google Lighthouse**
* **Chrome DevTools**
* **WAVE**
* **Google Rich Results / données structurées**

## Structure du projet

```text id="4xk7d3"
P4_Nina-Carducci-WebSite/
├── assets/
│   ├── bootstrap/
│   ├── images/
│   ├── maugallery.js
│   ├── scripts.js
│   └── style.css
├── .gitignore
└── index.html
```

Le dépôt contient actuellement un dossier `assets` regroupant les ressources du site ainsi que le fichier principal `index.html`.

## Résultats

L'intervention a permis d'obtenir une amélioration significative sur les principaux indicateurs Lighthouse.

| Critère          | Avant |   Après |
| ---------------- | ----: | ------: |
| Performance      |    64 | **100** |
| Accessibilité    |    67 |  **96** |
| SEO              |    73 | **100** |
| Bonnes pratiques |   100 | **100** |

Les résultats documentés après optimisation montrent ainsi des scores supérieurs à 90 dans toutes les catégories principales, avec **100 en Performance, 96 en Accessibilité, 100 en Best Practices et 100 en SEO**.

## Cahier de recette

Les principales corrections et optimisations ont été vérifiées à travers un cahier de recette.

| Élément testé                                 | Résultat            |
| --------------------------------------------- | ------------------- |
| Navigation précédente / suivante de la modale | ✅ Corrigé           |
| Affichage du filtre actif                     | ✅ Corrigé           |
| Chargement des images                         | ✅ Optimisé          |
| Balise `title`                                | ✅ Ajoutée           |
| Structure HTML sémantique                     | ✅ Améliorée         |
| Chargement JavaScript                         | ✅ Différé           |
| Meta SEO                                      | ✅ Ajoutées          |
| Attributs `alt`                               | ✅ Corrigés          |
| Labels du formulaire                          | ✅ Corrigés          |
| Référencement local                           | ✅ JSON-LD ajouté    |
| Partage sur réseaux sociaux                   | ✅ Open Graph ajouté |

## Défis rencontrés

Ce projet a principalement permis de travailler sur trois problématiques :

### Diagnostic d'un projet existant

Il a fallu comprendre une base de code existante avant de pouvoir intervenir efficacement. L’utilisation des DevTools et des breakpoints a permis d’observer l’exécution du JavaScript étape par étape et d’identifier les erreurs de logique.

### Optimisation des médias

La taille des images constituait un frein important aux performances. Leur conversion, leur compression, le lazy loading et la priorisation de l’image principale ont constitué les optimisations les plus importantes.

### Équilibre entre optimisation et périmètre du projet

Certaines améliorations supplémentaires étaient possibles, notamment la suppression de jQuery ou l’amélioration des contrastes. Elles n’ont pas été retenues comme priorités car le projet était déjà fonctionnel et les optimisations les plus impactantes avaient été traitées.

## Améliorations possibles

Pour aller plus loin, plusieurs pistes restent envisageables :

* remplacer complètement **jQuery** par du JavaScript natif ;
* améliorer certains contrastes de couleurs ;
* poursuivre l’optimisation des ressources ;
* optimiser davantage les images pour les différents formats d’écran.

La suppression de jQuery nécessiterait toutefois une refonte plus importante du fonctionnement existant.

## Bilan

Cette intervention a permis de transformer un site fonctionnel mais perfectible en une version **plus rapide, mieux référencée, plus accessible et plus robuste**.

Le travail réalisé a porté à la fois sur le code, les performances, le SEO, l’accessibilité et l’expérience utilisateur. Les optimisations ont notamment permis d'améliorer nettement les scores Lighthouse et de corriger les problèmes de navigation de la galerie.

## Auteur

**Elodie Chancerel**

Projet réalisé dans le cadre d’un projet d’audit et d’optimisation web.

### Repository

https://github.com/Daeliora/P4_Nina-Carducci-WebSite
