В чистом Маркдауне нет синтаксиса для таблиц, à GFM есть.

Premier en-tête | Deuxième en-tête
--- | ---
Cellule de contenu | Cellule de contenu
Cellule de contenu | Cellule de contenu

Для красоты можно и по бокам линии нарисовать:

Premier en-tête | Deuxième en-tête
--- | ---
Cellule de contenu | Cellule de contenu
Cellule de contenu | Cellule de contenu

Можно управлять выравниванием столбцов при помощи двоеточия.

Aligné à gauche | Centre aligné | Aligné à droite
:-- | :-: | --:
col 3 est | un texte verbeux | **1600 $**
col 2 est | centré | 12 $
rayures zébrées | sont soignés | ~~ $ 1 ~~

Dillinger est un éditeur de Markdown HTML5 optimisé pour le cloud, compatible mobile et hors ligne, AngularJS.

- Tapez du Markdown sur la gauche
- Voir HTML à droite
- la magie

# vrai

- Importez un fichier HTML et regardez-le comme par magie convertir en Markdown
- Faites glisser et déposez des images (nécessite que votre compte Dropbox soit lié)

Vous pouvez également:

- Importez et enregistrez des fichiers depuis GitHub, Dropbox, Google Drive et One Drive
- Faites glisser et déposez les fichiers de démarques et HTML dans Dillinger
- Exportez des documents au format Markdown, HTML et PDF

Markdown est un langage de balisage léger basé sur les conventions de formatage que les gens utilisent naturellement dans les e-mails. Comme [John Gruber] l'écrit sur le [site Markdown] [df1]

> L'objectif primordial de conception de la syntaxe de formatage de Markdown est de la rendre aussi lisible que possible. L'idée est qu'un document au format Markdown doit être publiable tel quel, en texte brut, sans avoir l'air d'avoir été balisé avec des balises ou des instructions de formatage.

Ce texte que vous voyez ici est en *réalité* écrit dans Markdown! Pour avoir une idée de la syntaxe de Markdown, tapez du texte dans la fenêtre de gauche et regardez les résultats dans la droite.

### faux

Dillinger utilise un certain nombre de projets open source pour fonctionner correctement:

- [AngularJS] - HTML amélioré pour les applications Web!
- [Ace Editor] - éditeur de texte Web génial
- [markdown-it] - Analyseur Markdown bien fait. Rapide et facile à étendre.
- [Twitter Bootstrap] - excellent passe-partout pour les applications Web modernes
- [node.js] - E / S avec événement pour le backend
- [Express] - infrastructure d'application réseau node.js rapide [@tjholowaychuk]
- [Gulp] - le système de construction en streaming
- [Breakdance](https://breakdance.github.io/breakdance/) - Convertisseur HTML en Markdown
- [jQuery] - duh

Et bien sûr, Dillinger lui-même est open source avec un [référentiel public] [aneth] sur GitHub.

### Installation

Dillinger nécessite [Node.js](https://nodejs.org/) v4 + pour fonctionner.

Installez les dépendances et devDependencies et démarrez le serveur.

```sh
$ cd dillinger
$ npm install -d
$ node app
```

Pour les environnements de production ...

```sh
$ npm install --production
$ NODE_ENV=production node app
```

### Plugins

Dillinger est actuellement étendu avec les plugins suivants. Les instructions sur la façon de les utiliser dans votre propre application sont liées ci-dessous.

Brancher | LISEZ-MOI
--- | ---
Dropbox | [plugins / dropbox / README.md] [PlDb]
GitHub | [plugins / github / README.md] [PlGh]
Google Drive | [plugins / googledrive / README.md] [PlGd]
OneDrive | [plugins / onedrive / README.md] [PlOd]
Moyen | [plugins / moyen / README.md] [PlMe]
Google Analytics | [plugins / googleanalytics / README.md] [PlGa]

### Développement

Vous souhaitez contribuer? Génial!

Dillinger utilise Gulp + Webpack pour un développement rapide. Modifiez votre fichier et consultez instantanément vos mises à jour!

Ouvrez votre terminal préféré et exécutez ces commandes.

Premier onglet:

```sh
$ node app
```

Deuxième onglet:

```sh
$ gulp watch
```

(facultatif) Troisième:

```sh
$ karma test
```

#### Construire pour la source

Pour la mise en production:

```sh
$ gulp build --prod
```

Génération d'archives zip pré-construites pour la distribution:

```sh
$ gulp build dist --prod
```

### Docker

Dillinger est très facile à installer et à déployer dans un conteneur Docker.

Par défaut, le Docker exposera le port 8080, modifiez-le si nécessaire dans le Dockerfile. Lorsque vous êtes prêt, utilisez simplement le Dockerfile pour créer l'image.

```sh
cd dillinger
docker build -t joemccann/dillinger:${package.json.version} .
```

Cela va créer l'image Dillinger et tirer les dépendances nécessaires. Assurez-vous d'échanger `${package.json.version}` avec la version actuelle de Dillinger.

Une fois cela fait, exécutez l'image Docker et mappez le port sur ce que vous souhaitez sur votre hôte. Dans cet exemple, nous mappons simplement le port 8000 de l'hôte au port 8080 du Docker (ou tout autre port exposé dans le Dockerfile):

```sh
docker run -d -p 8000:8080 --restart="always" <youruser>/dillinger:${package.json.version}
```

Vérifiez le déploiement en accédant à votre adresse de serveur dans votre navigateur préféré.

```sh
127.0.0.1:8000
```

#### Kubernetes + Google Cloud

Voir [KUBERNETES.md](https://github.com/joemccann/dillinger/blob/master/KUBERNETES.md)

### Todos

- Ecrire PLUS de tests
- Ajouter le mode nuit

## Licence

MIT
