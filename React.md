# Node Package Manager (npm + yarn)

### Install yarn if needed
```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn
```

### Make sure we have ./node_modules/.bin in our $PATH
```
echo $PATH
```
Add it if missing (change the 'export PATH' line, save and relaunch terminal):
```
code ~/zshrc
```

### Start a new front-end project (use UNLICENCED if private project)
```
cd ~/code/0r4nd
mkdir myproject && cd $_
yarn init
```
Setup git:
```
echo "node_modules" >> .gitignore
git init
git add .
git commit -m "Init repo"
```
Open the project with VSSCODE
```
code .
```

### Add some packages

eslint:
```
yarn add eslint --dev
eslint --init
git add .
git commit -m "Added ESLint"
```
setup .eslintrc.json
```
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": "airbnb-base",
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module"
    },
    "rules": {
      "no-console": "off",
      "comma-dangle": "off",
      "quotes": "off"
    }
}
```

webpack:
```
yarn add webpack webpack-dev-server webpack-cli html-webpack-plugin --dev
```

### Basic configuration
```
touch index.html
echo -e "<\!DOCTYPE html>\n<html>\n  <head>\n    <meta charset=\"UTF-8\">\n  </head>\n  <body>\n    <script src=\"dist/bundle.js\"></script>\n  </body>\n</html>\n" >> index.html

mkdir src
touch src/index.js
```


### Developing

Run local dev server:
```
webpack-dev-server
```


### Commands
- ```npm start``` Starts the development server.
- ```npm run build``` Bundles the app into static files for production.
- ```npm test``` Starts the test runner.
- ```Ctrl+C``` Stops the development server.

# Generic Util Functions
