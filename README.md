# RePOP boutique — site vitrine

Site web d'une seule page pour **RePOP boutique**, magasin de jouets et pop culture
(neuf & seconde main) situé **24 place d'Armes, 16700 Ruffec**.

- **Site en ligne :** https://repop-boutique.vercel.app
- **Type :** page statique, aucun serveur, aucune base de données
- **Objectif :** vitrine + référencement local (Nord Charente / Sud Vienne)

---

## Contenu du dépôt

| Fichier / dossier | Rôle |
|---|---|
| `index.html` | **Toute la page** : structure, styles (CSS dans `<head>`), et le petit script du diaporama. C'est le seul fichier à modifier pour changer le texte ou la mise en page. |
| `assets/logo.jpg` | Le logo rond (affiché en haut de la page) |
| `assets/shop.jpg` | Photo de la devanture (bandeau + image de partage sur les réseaux) |
| `assets/s1.jpg … s4.jpg` | Photos du diaporama (devanture + intérieurs) |
| `favicon.ico`, `icon-512.png`, `apple-touch-icon.png` | Icônes d'onglet / d'écran d'accueil (générées depuis le logo) |
| `site.webmanifest` | Métadonnées d'application web |
| `robots.txt`, `sitemap.xml` | Fichiers pour l'indexation Google |

Il n'y a **pas** de `package.json`, pas de `npm install`, pas d'étape de build.

---

## Comment modifier le site

1. Ouvrir `index.html` dans un éditeur de texte.
2. Modifier le texte / les liens directement dans le HTML.
   - Les caractères accentués sont écrits en entités (`&#233;` = é, `&#224;` = à…) pour éviter tout souci d'encodage. On peut aussi écrire les accents normalement, la page déclare `<meta charset="utf-8">`.
3. Pour changer une photo : remplacer le fichier dans `assets/` en **gardant le même nom**.
   - Format conseillé : JPEG, largeur ~1200 px, poids < 200 Ko.
4. Enregistrer, puis publier (voir ci-dessous).

Éléments souvent à mettre à jour :
- **Horaires** : chercher `Du lundi au samedi` dans `index.html` (et dans le bloc `openingHoursSpecification` du script `application/ld+json`).
- **Événements** : section `<section id="events">` (cartes « Défi de Ligue Pokémon », « Bourse d'échanges », etc.).
- **Réseaux sociaux** : liens Instagram / TikTok / Facebook / Vinted dans le menu (`<nav class="navlinks">`) et le pied de page (`<div class="socials">`).

---

## Comment le site se publie (déploiement)

Le site est hébergé sur **Vercel**, connecté à ce dépôt GitHub.

> **Chaque `git push` sur la branche `main` redéploie automatiquement le site**
> (environ 30 secondes). Aucune manipulation supplémentaire.

```bash
git add -A
git commit -m "Description de la modification"
git push
```

On peut aussi éditer un fichier directement sur github.com (bouton crayon) : le commit
déclenche le même déploiement automatique.

---

## Comptes et accès (à jour lors de la passation)

| Service | À quoi ça sert | Propriétaire visé |
|---|---|---|
| **GitHub** (`repop-boutique`) | code source | compte des propriétaires de la boutique |
| **Vercel** (projet `repop-boutique`) | hébergement + statistiques de visite (onglet *Analytics*) | compte Vercel des propriétaires |
| **Google Search Console** | suivi du référencement, envoi du `sitemap.xml` | compte Google `repop.boutique@gmail.com` |
| **Google Business Profile** | fiche Google Maps / recherche locale (la plus importante pour attirer des visiteurs) | déjà aux propriétaires — y ajouter le lien du site |

### Statistiques de visite
Onglet **Analytics** du projet sur vercel.com. Le script de suivi est déjà dans
`index.html` (`<script defer src="/_vercel/insights/script.js">`). Rien à installer.

---

## Ce qu'il reste à faire

- [ ] Confirmer les **horaires exacts** (coupure méridienne ? jour de fermeture ?)
- [ ] Mettre à jour ou rendre générique l'**événement Pokémon daté**
- [ ] Ajouter la propriété dans **Google Search Console** + soumettre `sitemap.xml`
      (méthode « balise HTML » : coller la balise `google-site-verification` dans le `<head>`)
- [ ] Compléter la **fiche Google Business Profile** et y mettre le lien du site
- [ ] Ajouter le lien du site dans les **bios Instagram / TikTok / Facebook**
- [ ] (Optionnel) nom de domaine personnalisé (ex. `repop.boutique`, ~4 $/an) —
      à acheter puis brancher dans Vercel → Settings → Domains, et mettre à jour
      les URL `canonical` / `og:url` / `sitemap.xml` dans le code.
- [ ] **Mentions légales** : compléter la forme juridique et le n° SIRET dans le
      bloc « Mentions légales » en bas de page (`index.html`, section `<details class="legal">`).

### Décisions éditoriales en attente (audit externe de sept. 2026)

Un audit fait par une autre IA a soulevé ces points ; volontairement laissés
de côté pour l'instant, à trancher par les propriétaires :

- [ ] Repositionner le message d'accueil : le ton actuel (« version collectionneur »)
      met surtout en avant Funko/Pokémon/vintage, alors que l'offre réelle est
      plus large (jouets classiques, jeux de société, cadeaux...).
- [ ] Ajouter un bloc « Nouveautés / Arrivages de la semaine » avec des photos
      récentes — demande une mise à jour régulière, pas un contenu figé.
- [ ] Préciser les conditions de reprise/rachat (espèces ou bon d'achat ?
      sur rendez-vous ?) — actuellement volontairement vague, faute d'info.
- [ ] Confirmer stationnement à proximité et accès PMR.
- [ ] Vérifier une mention trouvée sur une ancienne page de la mairie de Ruffec
      indiquant une adresse différente (« 5 place Aristide Briand ») pour un
      magasin de jouets — probablement un autre commerce, à vérifier par prudence.

---

*Site conçu en septembre 2026. Design « pop rétro », palette et logo tirés de
l'identité RePOP. Photos : Google Maps (fiche RePOP) et page Facebook.*
