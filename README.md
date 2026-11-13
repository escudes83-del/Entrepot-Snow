# Applis entrepôt

Applis web pour savoir où est rangé le matériel dans l'entrepôt, et pour recevoir les commandes du magasin.
Un dossier par rayon. Chaque rayon a son appli **Entrepôt** et son appli **Magasin**, avec son propre stock en ligne.

| Rayon | Entrepôt | Magasin | Dossier |
|---|---|---|---|
| Snow (bottes, fixations, snowboards) | `snow/index.html` | `snow/magasin.html` | `snow/` |
| Ski (chaussures de ski, skis) | `ski/index.html` | `ski/magasin.html` | `ski/` |

Adresses : `https://<compte>.github.io/<dépôt>/snow/` pour le snow, `https://<compte>.github.io/<dépôt>/ski/` pour le ski.
Un futur rayon aura son propre dossier, sur le même modèle que `ski/`.

À la racine, `index.html`, `magasin.html` et `magasin-snow.html` renvoient vers `snow/` : les applis déjà installées sur les téléphones continuent de marcher.

## Ce que font les applis

- **Rechercher** : par marque, modèle, taille, homme/femme. Chaque article affiche son emplacement (ex. `D1.2`).
- **Plan** : plan 2D et 3D de l'entrepôt, avec le stock en direct et les emplacements trouvés en orange.
- **Déplacer** : choisir des boîtes et les mettre ailleurs (à gauche ou à droite du niveau).
- **Arrivage** : noter ce qui arrive, puis plan de rangement d'après les mesures.
- **Commandes** : le magasin envoie une demande, l'entrepôt prépare, puis prévient le magasin.
- **Réglages** : listes, dimensions, historique des modifications, sauvegardes (une par jour, 30 jours).
- **↶ Annuler** : en haut de l'écran, annule la dernière modification du stock.
- **Côté Magasin** : *Commander*, *Chercher*, *Pick-up* (on prend soi-même une boîte à l'entrepôt), *Mes commandes*.

## Données partagées (Firebase)

Projet Firebase **entrepotsnow**, connexion anonyme. Chaque article est un document à part (pas d'écrasement entre deux personnes).
Collections : snow = `arts`, `orders`, `notifs`, `journal`, `backups`, `cfg` ; ski = les mêmes précédées de `ski_`.

- **Essais sans toucher aux vraies données** : ajoutez `?ns=test` à l'adresse (ex. `ski/magasin.html?ns=test`).
- Les fichiers de stock (`.json`) et les inventaires Excel ne vont **jamais** sur GitHub.

## Mise en ligne avec GitHub Pages

Le dossier `github` de l'ordinateur est une copie exacte du dépôt : on y dépose les fichiers changés (glisser aussi les dossiers `snow` et `ski` entiers).
Dans le dépôt : **Settings → Pages → Branch : main / (root)**.
