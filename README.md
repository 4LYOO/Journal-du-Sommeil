# Journal du sommeil 🌙

Application pour noter ses nuits (coucher, endormissement, réveils, siestes,
conditions, produits pris, impression générale) et suivre ses statistiques.

C'est une **application web installable** (PWA) : une fois mise en ligne, elle
s'ajoute à l'écran d'accueil de l'iPhone avec sa propre icône, s'ouvre en plein
écran et fonctionne **sans connexion**.

## Fichiers

| Fichier | Rôle |
| --- | --- |
| `index.html` | toute l'application |
| `manifest.webmanifest` | nom, icône et couleurs de l'application installée |
| `sw.js` | fonctionnement hors ligne |
| `icons/` | icônes (iPhone, Android, navigateur) |

## Mettre l'application en ligne (GitHub Pages, gratuit)

1. Sur GitHub, ouvrir le dépôt → **Settings** → **Pages**.
2. Dans **Build and deployment**, choisir **Source : Deploy from a branch**,
   puis la branche qui contient l'application (`main` une fois les changements
   fusionnés) et le dossier **/ (root)**. Cliquer sur **Save**.
3. Après une minute environ, l'adresse s'affiche en haut de la page, par exemple
   `https://4lyoo.github.io/journal-du-sommeil/`.

> GitHub Pages gratuit ne fonctionne qu'avec un dépôt **public**. Les nuits
> saisies ne sont jamais envoyées sur GitHub : elles restent sur le téléphone.

## Installer sur iPhone

1. Ouvrir l'adresse dans **Safari**.
2. Toucher **Partager** (carré avec une flèche) → **Sur l'écran d'accueil** → **Ajouter**.
3. Lancer ensuite l'application depuis son icône « Sommeil ».

Sur Android : ouvrir l'adresse dans Chrome → menu ⋮ → **Installer l'application**.

## Utilisation au quotidien

- **Le soir** : bouton **Je me couche** (barre en bas de l'onglet Saisie) : la mise
  au lit est notée à l'heure actuelle, sur la nuit qui se termine le lendemain.
- **Le matin** : **Je me lève**, puis **Assistant** : une question par écran,
  grande heure tactile, boutons ±5 / ±15 min, valeurs habituelles proposées,
  récapitulatif avant d'enregistrer. « Formulaire complet » reste accessible.
- **Formulaire complet** : toutes les cases, avec puces « habituel » et valeurs
  fréquentes, bouton ↩ par champ pour reprendre la valeur de la veille, alertes
  douces en cas d'incohérence, nuits manquantes signalées.
- **Historique** : calendrier du mois (couleur = impression, pointillés = nuit
  non saisie ; toucher un jour pour l'ouvrir), puis la liste des nuits.
- **Stats** : carte Tendances (7 jours), graphiques, comparaisons.
- **Mode nuit** : de 0 h à 5 h, l'interface passe d'elle-même en teintes ambrées.

Une copie de la version précédente est conservée dans `index.backup.html`.

## Sauvegarde des données (important)

Les nuits sont enregistrées **uniquement sur l'appareil**. Pour ne rien perdre :

- Onglet **Importer** → **Enregistrer une sauvegarde** : crée un fichier
  `journal-sommeil-AAAA-MM-JJ.json` à ranger dans Fichiers / iCloud Drive.
- **Restaurer depuis un fichier** recharge toutes les nuits (par exemple sur un
  nouveau téléphone). Les nuits du fichier remplacent celles des mêmes dates.
- L'onglet **Historique** permet aussi d'exporter en CSV (tableur) ou de tout
  copier au format note.

## Lien avec l'app Santé

Le bouton « Envoyer vers Santé » lance un raccourci iOS nommé
**Journal sommeil**, à créer une fois dans l'app Raccourcis. Il reçoit un texte
JSON avec les heures de coucher, d'endormissement, de réveil et de lever.
(Non testé.)

## Mettre à jour l'application

À chaque modification des fichiers, augmenter `VERSION` en haut de `sw.js`
(ex. `sommeil-v8`) et `APP_VERSION` dans `index.html` (ex. `8`).

L'application vérifie les mises à jour à l'ouverture et à chaque retour dans
l'app, puis se recharge toute seule (la saisie en cours est enregistrée avant).
Le numéro de version affiché en bas de l'onglet **Importer** permet de vérifier
quelle version tourne sur le téléphone.
