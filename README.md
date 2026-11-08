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

Après une modification des fichiers, changer la valeur `VERSION` en haut de
`sw.js` (par ex. `sommeil-v2`) pour que les téléphones récupèrent la nouvelle
version.
