# AndroidTV Links — MOD-PROD

PWA pour grand écran : une grille de tuiles où tu ajoutes tes propres liens avec la télécommande. Les liens personnels restent enregistrés dans le navigateur de l’appareil.

## Tuile Govioz (2e tuile)

La deuxième tuile est réservée à Govioz. Un workflow GitHub Actions lance le scraper toutes les heures (et peut être lancé manuellement). Il analyse la page Govioz à la recherche d’une annonce explicite de nouvelle adresse, extrait le lien associé, vérifie que le nouveau site répond, puis met à jour `data/govioz.json`. L’application synchronise alors automatiquement l’adresse de la tuile Govioz. En l’absence d’annonce fiable ou en cas d’erreur, l’adresse précédente est conservée.

**Important :** le scraper s’exécute sur GitHub Actions, pas dans le navigateur ni sur GitHub Pages. Dans les paramètres du dépôt GitHub, vérifier que les Actions sont autorisées et que le workflow dispose de la permission d’écriture du contenu (`Settings > Actions > General > Workflow permissions > Read and write permissions`).

## Utilisation

- Tuile « + Ajouter » : formulaire nom + adresse (complétée en `https://`).
- « Mode édition » puis OK sur une tuile : modifier ou supprimer.
- Flèches + OK pour naviguer, Retour pour fermer le formulaire.

## Fichiers

```
index.html                  interface + gestion des liens
data/govioz.json            adresse synchronisée de Govioz
scripts/update_govioz.py    scraper d’annonces de changement d’adresse
.github/workflows/          exécution automatique horaire
manifest.json               PWA (nom, icônes, plein écran)
sw.js                       service worker
```

## Publier sur GitHub Pages

1. Settings > Pages
2. Source : **Deploy from a branch** — Branch : `main` — Dossier : `/ (root)` — Save
3. Dans Settings > Actions > General, autoriser les workflows et donner la permission `Read and write` au contenu du dépôt.
4. Après environ une minute : `https://TON_COMPTE.github.io/NOM_DU_DEPOT/`

Après une modification du cache PWA, incrémenter `CACHE` dans `sw.js`.
