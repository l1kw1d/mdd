# Maçonnerie David Deschambault Inc. — Site web

Site statique pour Maçonnerie David Deschambault Inc., basée à **Saint-Stanislas-de-Kostka** et au service du **Suroît, Vaudreuil-Soulanges et de la Montérégie**. Conçu pour être déployé sur **Vercel**, sans build, sans framework, sans dépendance.

## Structure

```
maconneriemdd/
├── index.html        Site complet (CSS et JS inline)
├── robots.txt        SEO + politique IA (GPTBot, PerplexityBot, ClaudeBot autorisés)
├── sitemap.xml       Plan du site avec sitemap d'images
├── vercel.json       Headers de sécurité, cache long terme
└── README.md         Ce fichier
```

> Les images sont chargées depuis `maconneriemdd.com` (les images existantes du client). Quand le site sera déployé sur ce même domaine, elles fonctionneront. Pour héberger localement, télécharger les images dans `/assets/images` et remplacer les URLs dans `index.html`.

## Déploiement Vercel (3 minutes)

**Option 1, drag & drop**
1. Aller sur [vercel.com/new](https://vercel.com/new)
2. Glisser-déposer le dossier `maconneriemdd/`
3. Cliquer Deploy

**Option 2, CLI**
```bash
npm i -g vercel && cd maconneriemdd && vercel --prod
```

**Domaine** : Settings → Domains → ajouter `maconneriemdd.com` et `www.maconneriemdd.com`.

## Conformité Loi 25

Le site contient un lien vers la politique de confidentialité existante (`https://privacy.maconneriemdd.com`), conforme à la Loi 25 du Québec. Ce lien apparaît dans le pied de page.

Si vous ajoutez un formulaire avec stockage de données ou de l'analytique (Google Analytics, Plausible, etc.), il faut :
- Mettre à jour la politique de confidentialité pour mentionner ces collectes
- Ajouter une bannière de consentement aux cookies (essentiel si vous utilisez des cookies non-essentiels)
- Tenir un registre des activités de traitement (RAT)

## Stratégie SEO ciblée

### Localisation réelle
L'atelier est situé à **Saint-Stanislas-de-Kostka**, dans la MRC de Beauharnois-Salaberry, sur la rive sud du fleuve Saint-Laurent à environ 80 km au sud-ouest de Montréal. Les zones de service couvrent le **Suroît, Vaudreuil-Soulanges et le Haut-Saint-Laurent**.

### Mots-clés cibles

| Mot-clé | Volume estimé | Présence |
|---|---|---|
| Rejointoiement | Très haute | H3, FAQ, Schema |
| Briqueteur-maçon | Haute | Eyebrow, About, Schema |
| Maçon Suroît | Haute | Title, Description |
| Maçon Vaudreuil-Soulanges | Moyenne | Title, Schema |
| Réparation brique | Haute | Service #02, FAQ |
| Ventre de bœuf | Moyenne, haute conversion | Service, FAQ |
| Allèges et linteaux | Moyenne | Services |
| Long-tail par ville (20 villes) | Volume cumulé important | Section Territoire visible + Schema |

### Données structurées (Schema.org)

Triple Schema :
1. **`LocalBusiness` + `GeneralContractor` + `HomeAndConstructionBusiness`** avec 25 zones desservies
2. **`Service` × 3** (rejointoiement, restauration, cheminées)
3. **`FAQPage`** avec 6 questions, alignées au contenu visible

Ce qui n'a **pas** été inclus dans le Schema (pour rester honnête) :
- Pas d'`aggregateRating` tant qu'il n'y a pas de vrais avis publiés
- Pas de `priceRange`, `paymentAccepted` ni `openingHours` non confirmés par le client
- Pas de promesses de garantie ou de certification non confirmées

### Bots IA (AEO)

`robots.txt` autorise GPTBot, PerplexityBot, ClaudeBot, Google-Extended. Quand quelqu'un demande à un assistant IA un maçon dans le Suroît, le site est éligible comme source.

## Sections du site

1. **Hero**, titre éditorial, lede, stats du site original (25 ans, 100+ projets), CTA
2. **L'atelier** (#01), David Deschambault, RBQ visible, basé à Saint-Stanislas-de-Kostka
3. **Le métier** (#02), 5 services avec mots-clés en H3 + 14 sous-services
4. **Notre méthode** (#03), 4 étapes du processus
5. **Réalisations** (#04), galerie bento de 6 projets
6. **Pourquoi nous** (#05), 3 valeurs : RBQ, réponse 24h ouvrables, supervision directe
7. **Territoire** (#06), 20 villes desservies + carte SVG du Suroît avec atelier à St-Stanislas
8. **FAQ** (#07), 6 questions, alignées au Schema
9. **Contact** (#08), méthodes + formulaire (mailto, pas de backend)
10. **Footer**, colonnes + RBQ + politique de confidentialité

## Personnalisation rapide

| Pour modifier… | Va dans `index.html` et cherche… |
|---|---|
| Téléphone | `+14502681610` |
| Email | constantes `emailUser` et `emailDomain` dans `<script>` |
| Couleurs | bloc `:root` au début du `<style>` |
| Services / mots-clés H3 | section `class="services"` |
| Villes ciblées | section `id="zones"` ET le Schema en haut |
| FAQ | section `id="faq"` ET le Schema FAQPage |

## À faire pour aller plus loin

- **Vrais témoignages clients** avec accord écrit, à insérer dans une section dédiée
- **Photos professionnelles** de chantiers récents, plus impactantes que les actuelles
- **Avis Google** à activer dans le profil Google Business Profile, puis intégrer le widget
- **Backend formulaire** (Formspree, Resend, Vercel Functions) pour ne plus dépendre de mailto
- **Articles de blog** pour le SEO long-tail (un article par question typique)
- **Synchroniser avec Google Business Profile** : mêmes photos, mêmes infos, mêmes services

## Coordonnées

- Téléphone : 450 268-1610
- Adresse : Saint-Stanislas-de-Kostka, QC
- Facebook : [maconneriedaviddeschambault.inc](https://www.facebook.com/maconneriedaviddeschambault.inc)
- RBQ : 5667-9582-01
- Politique de confidentialité : [privacy.maconneriemdd.com](https://privacy.maconneriemdd.com)
