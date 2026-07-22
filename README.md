# Dashboard Service Utilisateur — mise à jour RTU

Cette version apporte deux ajustements d'affichage à la section RTU :

- lorsqu'un seul service est sélectionné, le **Statut** est présenté dans le même format que **Version RTU** et **Date de réception** ;
- lorsque plusieurs services sont affichés, les blocs **Version RTU** et **Date de réception** sont plus compacts (conteneurs et typographie réduits).

## Publication

Déposer `index.html`, `README.md` et `.nojekyll` à la racine du dépôt GitHub Pages, puis forcer le cache dans Grist avec un paramètre d'URL, par exemple `?v=1.14`.


## Mise à jour V1.15

Dans les cartes EMM du Dashboard Service Utilisateur, seul le nom de la colonne `Service Utilisateur` est désormais affiché. La valeur de la colonne `Service` n’est plus répétée sur la carte.


## Affichage Étape / Statut

- RTU, Réseau/Raccordement/Flux et Chantiers de conception : l'**Étape** est affichée en haut à droite ; le **Statut** reste visible dans le contenu de la carte.
- EMM : en l'absence de colonne Étape, le **Statut** est affiché en haut à droite.
- `En cours DT` est signalé en bleu clair et `Terminé` en vert ; les autres valeurs restent grises.
