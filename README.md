# Dashboard Service Utilisateur — V1.3 single-file

Cette version est volontairement livrée dans un seul `index.html` afin d’éviter les problèmes de cache ou de remplacement partiel de `app.js` / `styles.css` sur GitHub Pages.

## Correctifs

- JavaScript et CSS intégrés dans `index.html`;
- bouton **Configurer** actif avant tout appel à l’API Grist;
- badge visible `v1.3` pour confirmer la version chargée;
- appels API limités dans le temps;
- affichage non bloquant même si les métadonnées Grist sont indisponibles;
- détection élargie des anciens identifiants techniques de tables;
- configuration manuelle possible sans mapping natif.

Le widget nécessite **Full document access**.
