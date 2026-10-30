# TV Links (PWA) — MOD-PROD

PWA pour grand écran : une grille de tuiles où tu ajoutes tes propres liens avec la télécommande. Pas de serveur, pas de scraper. Les liens sont enregistrés dans le navigateur de l’appareil.

## Utilisation

- Tuile « + Ajouter » : formulaire nom + adresse (complétée en `https://`, http/https uniquement).
- « Mode édition » (en haut à droite) puis OK sur une tuile : modifier ou supprimer.
- Flèches + OK pour naviguer, Retour pour fermer le formulaire.

## Structure

```
public/
├── index.html      ← interface + gestion des liens
├── manifest.json   ← PWA (nom, icônes, plein écran)
├── sw.js           ← service worker (fonctionne hors ligne)
└── icon-*.png
vercel.json         ← en-têtes pour sw.js et manifest.json
```

## Déployer sur Vercel

1. Pousser ce dossier sur GitHub (nouveau dépôt « AndroidTv-Links »).
2. vercel.com > New Project > importer le dépôt > Framework « Other » > Deploy.
3. Ouvrir l’adresse obtenue (HTTPS) sur la TV, puis installer / ajouter à l’écran d’accueil si le navigateur le propose.

## Local

```
npx serve public
```

Après une modification, incrémenter `CACHE` dans `public/sw.js` pour forcer la mise à jour.
