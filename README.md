<div align="center">

# Maçonnerie David Deschambault Inc.

**Site web officiel — refonte 2026**

Site statique, sans build, sans framework, sans base de données. Conçu pour être déployé sur Vercel et battre la concurrence locale en SEO sur le secteur du Suroît, Vaudreuil-Soulanges et de la Montérégie.

[![Site](https://img.shields.io/badge/site-maconneriemdd.com-c45a3a?style=flat-square)](https://maconneriemdd.com)
[![RBQ](https://img.shields.io/badge/RBQ-5667--9582--01-1c2025?style=flat-square)](https://www.rbq.gouv.qc.ca)
[![Deploy](https://img.shields.io/badge/deploy-Vercel-000?style=flat-square&logo=vercel)](https://vercel.com)
[![License](https://img.shields.io/badge/license-Propriétaire-555?style=flat-square)](#-licence)
[![Loi 25](https://img.shields.io/badge/Loi%2025-conforme-2d8659?style=flat-square)](https://privacy.maconneriemdd.com)

</div>

---

## 📖 Table des matières

- [Aperçu](#-aperçu)
- [Stack technique](#-stack-technique)
- [Démarrage rapide](#-démarrage-rapide)
- [Déploiement](#-déploiement)
- [Structure du projet](#-structure-du-projet)
- [Architecture du site](#-architecture-du-site)
- [SEO et données structurées](#-seo-et-données-structurées)
- [Conformité Loi 25](#-conformité-loi-25)
- [Personnalisation](#-personnalisation)
- [Performance](#-performance)
- [Accessibilité](#-accessibilité)
- [Roadmap](#-roadmap)
- [Coordonnées](#-coordonnées)
- [Licence](#-licence)

---

## 🎯 Aperçu

Site « one-pager » pour Maçonnerie David Deschambault Inc., briqueteur-maçon basé à Saint-Stanislas-de-Kostka. Le site cible principalement les recherches Google locales (rejointoiement, réparation de brique, restauration patrimoniale) sur le secteur du Suroît, Vaudreuil-Soulanges et du Haut-Saint-Laurent.

**Direction artistique** : éditorial brutaliste, palette minérale (mortier froid, argile québécoise, acier graphite), typographie distinctive (Fraunces, Inter, JetBrains Mono).

**Promesse** : pas de fausses promesses, pas d'inventions. Tout le contenu est vérifiable. Le site est honnête sur ce qu'il sait et ne sait pas.

---

## 🛠 Stack technique

| Couche | Choix | Pourquoi |
|---|---|---|
| HTML | HTML5 sémantique | Standards web, accessibilité, SEO |
| CSS | CSS natif inline | Pas de build, pas de Tailwind, performance maximale |
| JS | Vanilla ES6+ | Pas de framework, ~3 KB de JS au total |
| Polices | Google Fonts (Fraunces, Inter, JetBrains Mono) | Préchargées, `display=swap` |
| Hébergement | Vercel (statique) | CDN global, HTTPS automatique, déploiement instantané |
| Données structurées | JSON-LD Schema.org | LocalBusiness + Service + FAQPage + BreadcrumbList |

**Aucune dépendance npm. Aucun build step. Aucune base de données.** Le site est un seul fichier `index.html` qui peut être ouvert directement dans un navigateur.

---

## 🚀 Démarrage rapide

### Prérequis
Aucun. Un navigateur suffit.

### Lancer en local

```bash
git clone https://github.com/<owner>/maconneriemdd.git
cd maconneriemdd
```

Ouvrir `index.html` dans un navigateur, ou servir le dossier avec n'importe quel serveur statique :

```bash
# Option 1 : Python
python3 -m http.server 8000

# Option 2 : Node
npx serve .

# Option 3 : Vercel CLI
npx vercel dev
```

Le site est ensuite accessible sur `http://localhost:8000`.

---

## ☁️ Déploiement

### Sur Vercel (recommandé)

**Drag & drop**

1. Aller sur [vercel.com/new](https://vercel.com/new)
2. Glisser-déposer le dossier
3. Cliquer sur **Deploy**

**Via Git**

```bash
vercel link
vercel --prod
```

Aucune commande de build, aucune variable d'environnement nécessaire. Le fichier `vercel.json` configure les en-têtes de sécurité et le cache.

### Domaine personnalisé

Dans Vercel : **Settings → Domains** → ajouter `maconneriemdd.com` et `www.maconneriemdd.com`. Les enregistrements DNS à configurer chez le registrar sont fournis par Vercel.

### Hébergement alternatif

Le site fonctionne sur n'importe quel hébergeur statique : Netlify, Cloudflare Pages, GitHub Pages, AWS S3 + CloudFront, etc. Aucune adaptation nécessaire (sauf le fichier `vercel.json` qui est spécifique à Vercel).

---

## 📁 Structure du projet

```
maconneriemdd/
├── index.html          # Site complet (HTML + CSS inline + JS inline)
├── robots.txt          # Politique d'exploration (incl. bots IA)
├── sitemap.xml         # Plan du site avec sitemap d'images
├── vercel.json         # En-têtes de sécurité et règles de cache
└── README.md           # Ce fichier
```

> **Note sur les images** : actuellement chargées depuis `https://maconneriemdd.com/assets/images/` (les images du site existant). Quand le site sera déployé sur ce domaine, elles fonctionneront automatiquement. Pour les héberger localement, créer `/assets/images/` et mettre à jour les URLs dans `index.html`.

---

## 🏗 Architecture du site

Le site est un « one-pager » avec navigation par ancres. Les sections sont numérotées comme un magazine éditorial.

| # | Section | Anchor | Contenu |
|---|---|---|---|
| | Hero | `#` | Titre éditorial, lede, statistiques, CTA |
| 01 | L'atelier | `#expertise` | Présentation, RBQ visible, signature de David |
| 02 | Le métier | `#metier` | 5 services principaux + 14 sous-services |
| 03 | Notre méthode | (process) | 4 étapes : estimation, planification, exécution, suivi |
| 04 | Réalisations | `#realisations` | Galerie « bento » de 6 projets |
| 05 | Pourquoi nous | (values) | RBQ, réponse 24 h, supervision directe |
| 06 | Territoire | `#zones` | 20 villes desservies + carte SVG du Suroît |
| 07 | FAQ | `#faq` | 6 questions fréquentes (alignées au Schema) |
| 08 | Contact | `#contact` | Méthodes + formulaire (mailto) |
| | Footer | | Colonnes + politique de confidentialité |

---

## 🔍 SEO et données structurées

### Mots-clés cibles

| Mot-clé | Volume estimé | Intention | Présence |
|---|---|---|---|
| `rejointoiement` | Très haute | Commerciale | H3, FAQ, Schema |
| `briqueteur-maçon` | Haute | Commerciale | Eyebrow, About, Schema |
| `maçon Suroît` | Haute | Locale | `<title>`, description |
| `maçon Vaudreuil-Soulanges` | Moyenne | Locale | `<title>`, Schema |
| `réparation brique` | Haute | Commerciale | Service #02, FAQ |
| `ventre de bœuf` | Moyenne | Urgence (haute conversion) | Service, FAQ |
| `allèges et linteaux` | Moyenne | Technique | Services |
| Long-tail × 20 villes | Volume cumulé important | Locale précise | Section Territoire (visible) + Schema |

### Données structurées (JSON-LD)

Le site implémente un graphe de données structurées Schema.org avec 6 nœuds :

```
@graph
├── LocalBusiness + GeneralContractor + HomeAndConstructionBusiness
│   ├── 25 areaServed (régions et villes)
│   ├── 21 knowsAbout (compétences)
│   └── identifier RBQ
├── Service: Rejointoiement
├── Service: Restauration patrimoniale
├── Service: Cheminées et foyers
├── FAQPage (6 questions, alignées avec le contenu visible)
└── BreadcrumbList
```

**Ce qui n'est PAS dans le Schema** (pour rester honnête) :

- ❌ Pas de `aggregateRating` tant qu'il n'y a pas de vrais avis publiés
- ❌ Pas de `priceRange` ni `paymentAccepted` non confirmés
- ❌ Pas de `openingHoursSpecification` non vérifié

### Bots et moteurs de réponse (AEO)

Le `robots.txt` autorise explicitement les bots des assistants IA :

```
User-agent: GPTBot          → Allow: /
User-agent: PerplexityBot   → Allow: /
User-agent: ClaudeBot       → Allow: /
User-agent: Google-Extended → Allow: /
```

Quand un utilisateur demande à ChatGPT, Perplexity ou Claude « qui peut faire mes joints de brique dans le Suroît ? », le site est éligible comme source.

### Outils de validation

- [Rich Results Test (Google)](https://search.google.com/test/rich-results)
- [Schema Markup Validator](https://validator.schema.org)
- [PageSpeed Insights](https://pagespeed.web.dev)

---

## 🇶🇨 Conformité Loi 25

Le site est conforme à la [Loi 25 du Québec](https://www.cai.gouv.qc.ca/) sur la protection des renseignements personnels :

- ✅ Lien vers la politique de confidentialité dans le pied de page → [privacy.maconneriemdd.com](https://privacy.maconneriemdd.com)
- ✅ Aucune collecte de données personnelles côté client (pas de formulaire avec stockage)
- ✅ Aucun cookie tiers ni script de tracking
- ✅ Le formulaire de contact utilise `mailto:`, qui ouvre simplement le client mail de l'utilisateur

### Si vous ajoutez de l'analytique ou un backend

Si à l'avenir vous ajoutez Google Analytics, Plausible, un formulaire avec stockage, ou tout autre outil collectant des données, il faudra :

1. Mettre à jour la politique de confidentialité pour mentionner cette collecte
2. Ajouter une bannière de consentement aux cookies (essentiel si cookies non-essentiels)
3. Tenir un registre des activités de traitement (RAT)
4. Désigner un responsable de la protection des renseignements personnels

---

## ⚙️ Personnalisation

### Modifier les coordonnées

| Pour modifier… | Chercher dans `index.html` |
|---|---|
| Numéro de téléphone | `+14502681610` (4 occurrences) |
| Email | Constantes `emailUser` et `emailDomain` dans le `<script>` |
| Numéro RBQ | `5667-9582-01` |
| Adresse de l'atelier | `Saint-Stanislas-de-Kostka` |

### Modifier la palette

Les couleurs sont définies en variables CSS dans le bloc `:root` au début du `<style>` :

```css
:root {
  /* Bases minérales */
  --mortar:        #ecede9;   /* Fond principal, mortier frais */
  --mortar-soft:   #e0e1dc;   /* Mortier sec */
  --lime:          #f4f5f1;   /* Lait de chaux */
  --stone-cool:    #b8b9b3;   /* Pierre calcaire */
  --concrete:      #6e7176;   /* Béton brut */
  --steel:         #4a4e54;   /* Acier brossé */

  /* Argile québécoise (accent) */
  --clay:          #c45a3a;   /* Brique d'argile */
  --clay-deep:     #8e3d24;   /* Brique vieillie */
  --clay-glow:     #d97249;   /* Éclat de brique */

  /* Profondeurs */
  --graphite:      #1c2025;   /* Anthracite acier */
  --graphite-deep: #12161a;   /* Nuit graphite */
  --char:          #2a2e34;   /* Texte foncé */
}
```

### Modifier les villes desservies

Les villes apparaissent à 3 endroits qui doivent rester synchronisés :

1. **Section visible** (`<section id="zones">`) → liste de 20 villes
2. **Carte SVG** (à l'intérieur de la section `zones`) → points et étiquettes
3. **Schema JSON-LD** (`@type: LocalBusiness`, propriété `areaServed`) → 25 entrées

> ⚠️ Les FAQ Schema doivent toujours correspondre au texte visible dans la section FAQ. Sinon, Google pénalise le site pour contenu caché.

### Modifier les services

Section `<section class="services">`. Les 5 services principaux sont en `<h3 class="service__title">`. Pour le SEO, gardez les mots-clés à fort volume en début de titre (rejointoiement, réparation, etc.).

---

## 📊 Performance

Le site est conçu pour des scores Lighthouse 95+ sur tous les axes (performance, accessibilité, bonnes pratiques, SEO).

| Métrique | Cible | Méthode |
|---|---|---|
| First Contentful Paint | < 1.0s | CSS inline, polices préconnectées |
| Largest Contentful Paint | < 1.8s | Images en `loading="lazy"`, hero text-only |
| Cumulative Layout Shift | < 0.1 | Polices `display=swap`, dimensions fixes |
| Total Blocking Time | < 200ms | JS minimal, pas de framework |
| Taille totale (sans images) | ~110 KB | Un seul fichier HTML |

### Cache et compression

Le fichier `vercel.json` configure :
- Cache long terme (1 an, immutable) sur les assets statiques
- Revalidation systématique sur le HTML
- HSTS, X-Frame-Options, Referrer-Policy, Permissions-Policy

---

## ♿ Accessibilité

- HTML5 sémantique (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- Attributs ARIA appropriés (`aria-label`, `aria-hidden`, `role`)
- Navigation au clavier complète (focus visible, tab order logique)
- Contraste de couleurs niveau AA (vérifié sur les paires principales)
- `prefers-reduced-motion` respecté (toutes les animations désactivées)
- Texte alternatif sur toutes les images significatives
- Formulaire avec `<label>` associés à chaque `<input>`

---

## 🗺 Roadmap

Améliorations suggérées par ordre de priorité business :

### Court terme

- [ ] Synchroniser le profil **Google Business Profile** (mêmes infos, mêmes photos, mêmes services que sur le site)
- [ ] Activer la collecte d'**avis Google** réels et les afficher sur le site
- [ ] Remplacer les images par des **photos professionnelles** de chantiers récents
- [ ] Ajouter de **vrais témoignages clients** (avec accord écrit) dans une nouvelle section

### Moyen terme

- [ ] Backend pour le formulaire de contact (Formspree, Resend, ou Vercel Functions)
- [ ] Page galerie complète avec filtres par type de travaux
- [ ] Slider avant/après sur les projets de restauration
- [ ] Articles de blog pour le SEO long-tail (un article par question typique)

### Long terme

- [ ] Espace client (devis en ligne, suivi de chantier)
- [ ] Calculateur d'estimation préliminaire (sans engagement)
- [ ] Intégration multilingue (anglais pour la clientèle anglophone du Suroît)

---

## 📞 Coordonnées

| | |
|---|---|
| Téléphone | [450 268-1610](tel:+14502681610) |
| Email | [info@maconneriemdd.com](mailto:info@maconneriemdd.com) |
| Adresse | Saint-Stanislas-de-Kostka, QC |
| Facebook | [maconneriedaviddeschambault.inc](https://www.facebook.com/maconneriedaviddeschambault.inc) |
| RBQ | [5667-9582-01](https://www.rbq.gouv.qc.ca) |

---

## 📄 Licence

© 2026 Maçonnerie David Deschambault Inc. Tous droits réservés.

Le code source de ce site est la propriété de Maçonnerie David Deschambault Inc. Le contenu (textes, images, marque) ne peut être réutilisé sans autorisation écrite préalable.

Les bibliothèques tierces utilisées (Google Fonts) restent sous leurs licences respectives.

---

<div align="center">

**Site conçu pour bâtir la confiance, brique par brique.**

</div>
