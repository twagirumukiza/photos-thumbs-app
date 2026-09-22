# Miniatures Photo — 220×160

Petite application web pour générer des **miniatures 220×160** et un fichier **ZIP** prêt à coller dans un carnet de voyage (structure `photos/` + `thumbs/`).

Tout se passe **dans le navigateur** : aucune photo n’est envoyée sur un serveur.

## Utilisation

1. Ouvre `index.html` (en local ou via GitHub Pages).
2. Indique le **nom de la galerie** (ex. `san-cristobal`, `palenque`).
3. Glisse ou sélectionne tes photos.
4. Clique sur **Générer le ZIP**.

Le ZIP contient :

```
san-cristobal/
├── 01.jpg
├── 02.jpg
├── …
└── thumbs/
    ├── 01.jpg   ← 220×160
    ├── 02.jpg
    └── …
```

## Déployer sur GitHub Pages

1. Crée un nouveau dépôt (ex. `photo-thumbs`).
2. Uploade `index.html` (et ce README si tu veux).
3. Settings → Pages → Source : **Deploy from a branch** → branche `main` → dossier `/ (root)`.
4. Ouvre `https://TON-USER.github.io/photo-thumbs/`.

## Détails techniques

- Miniatures : crop centré, JPEG qualité ~85 %.
- Grandes photos : converties en JPEG (qualité ~92 %) pour uniformiser les noms `.jpg`.
- Numérotation : `01`, `02`, … selon l’ordre alphabétique des fichiers d’origine.
- Bibliothèques CDN : [JSZip](https://stuk.github.io/jszip/) + [FileSaver.js](https://github.com/eligrey/FileSaver.js).

## Compatibilité

Fonctionne sur Chrome, Firefox, Edge, Safari récents.  
Les fichiers HEIC peuvent ne pas s’afficher selon le navigateur (convertis-les en JPEG avant si besoin).
