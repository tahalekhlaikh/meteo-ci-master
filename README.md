# default

## Project setup

```
# yarn
yarn

# npm
npm install

# pnpm
pnpm install
```

### Compiles and hot-reloads for development

```
# yarn
yarn dev

# npm
npm run dev

# pnpm
pnpm dev
```

### Compiles and minifies for production

```
# yarn
yarn build

# npm
npm run build

# pnpm
pnpm build
```

### Customize configuration

See [Configuration Reference](https://vitejs.dev/config/).


### Stage Test

Le stage « test » est composé de 7 jobs de tests statiques et un job pour les tests automatisés :

```
# test_jshint : 
- npm install -g jshint
- jshint src 

# test_standardJS :
- npm install standard --global
- npx standard

# test_stylelint : vérification syntaxique de base du code css.
- npm install -g csslint
- csslint --version
- csslint dist/assets/index.e2dd1dbf.css

# lint_eslint : Identifier les erreurs dans du code JavaScript.
- npm install eslint --save-dev
- npm run lint

# lint_html_validate : Valider la conformité des fichiers HTML aux normes W3C.
- npm install -g html-validate
- html-validate ./index.html

# lint_docker1 : tester le dockerfile1.
- hadolint ./Dockerfile1

# lint_docker2 : tester le dockerfile2.
- hadolint ./Dockerfile2

# test_Automation: tester les fonctionnalités de l’application de manière automatique avec Selenium Webdrive. 
Afin qu’on puisse mettre en place selenium dans notre job, on doit d’abord utiliser GeckoDriver qui est un lien de connexion vers le navigateur Firefox pour le script de test qu’on a créer avec Selenium (On peut aussi utiliser ChromeDriver pour les tests sur Google Chrome). 
Nous avons utilisé un bloc de code partagé qui contient l’installation et la configuration de GeckoDriver (nommé « install_firefox_geckodriver »).
- pip install 'selenium<4.0.0'
- pip install selenium pytest
- pytest

```
