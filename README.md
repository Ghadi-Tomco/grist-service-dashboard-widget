# Dashboard Service Utilisateur — Custom Widget Grist

Ce widget consolide, pour un service utilisateur donné ou pour l'ensemble des services :

- le suivi du RTU (`A_Suivi RTU`) ;
- les sujets Infra & Flux (`B_Infra & Flux`) ;
- les sujets EMM (`B_EMM`) ;
- les chantiers de conception (`B_Chantiers_de_conception`) ;
- les informations du référentiel des services (`REF_Services Utilisateurs`) ;
- les libellés d'acteurs (`REF_Acteurs`, facultatif).

Le widget lit plusieurs tables et permet de modifier les enregistrements dans leurs tables sources. Il nécessite donc **Full document access**.

## Installation GitHub Pages

1. Déposer à la racine d'un repository GitHub :
   - `index.html`
   - `styles.css`
   - `app.js`
   - `.nojekyll`
2. Dans GitHub : **Settings > Pages > Deploy from a branch > main > /(root)**.
3. Copier l'URL GitHub Pages générée.

## Installation dans Grist

1. Créer une page ou un widget `Custom` ; la table `DB_EMM_Dashboard` peut servir de table support.
2. Choisir `Custom URL` et coller l'URL GitHub Pages.
3. Accorder **Full document access**.
4. Aucun mapping de colonnes n'est nécessaire : le widget détecte les tables et les colonnes par leur identifiant et leur libellé.
5. Si une table n'est pas trouvée, cliquer sur **Configurer** et sélectionner son identifiant technique Grist.

## Fonctionnement

- Le sélecteur de service utilisateur est alimenté par `REF_Services Utilisateurs`.
- Sans service sélectionné, toutes les données sont affichées.
- Les lignes dont le service vaut `Tous` restent visibles pour chaque service sélectionné.
- Le clic sur un sujet ouvre un panneau latéral modifiable.
- Le widget détecte les colonnes `Text`, `Choice`, `ChoiceList`, `Date`, `DateTime`, `Ref` et `RefList`.
- Les références vers les services et les acteurs sont affichées avec leur libellé, mais les identifiants de référence sont conservés lors de l'écriture.
- Pour `B_EMM`, la date `Modifiée le` est actualisée à l'enregistrement.
- Pour les chantiers de conception, les timestamps de statut et d'étape sont actualisés lorsque ces valeurs changent.

## Tables attendues

Les identifiants techniques habituellement détectés sont :

- `A_Suivi_RTU`
- `B_Infra_Flux`
- `B_EMM`
- `B_Chantiers_de_conception`
- `REF_Services_Utilisateurs`
- `REF_Acteurs`

Les alias affichés peuvent contenir des espaces ou le caractère `&`.

## Sécurité

Le widget n'utilise aucune bibliothèque externe autre que l'API officielle Grist et ne réalise aucun appel réseau vers un service tiers. Le code source doit toutefois être hébergé sur un dépôt maîtrisé et relu avant mise en production, car l'accès complet permet de lire et modifier les tables du document Grist.
