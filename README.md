# AndroidTv Links — MOD-PROD

PWA pour grand écran : une grille de tuiles où tu ajoutes tes propres liens avec la télécommande. Pas de serveur. Les liens sont enregistrés dans le navigateur de l’appareil.

## Utilisation

- Tuile « + Ajouter » : formulaire nom + adresse (complétée en `https://`).
- « Mode édition » (en haut à droite) puis OK sur une tuile : modifier ou supprimer.
- Flèches + OK pour naviguer, Retour pour fermer le formulaire.

## Fichiers

```
index.html      ← interface + gestion des liens
manifest.json   ← PWA (nom, icônes, plein écran)
sw.js           ← service worker (fonctionne hors ligne)
icon-*.png
.nojekyll
```

## Publier sur GitHub Pages

1. Settings > Pages
2. Source : **Deploy from a branch** — Branch : `main` — Dossier : `/ (root)` — Save
3. Après environ une minute : `https://TON_COMPTE.github.io/NOM_DU_DEPOT/`

Après une modification, incrémenter `CACHE` dans `sw.js` pour forcer la mise à jour.
