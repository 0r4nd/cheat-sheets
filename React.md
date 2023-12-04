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

babel:
```
yarn add babel-core babel-preset-es2015 --dev
echo '{ "presets": [ "es2015" ] }' > .babelrc
yarn add babel-loader # for webpack
```

### Basic configuration
```
touch index.html
echo -e "<\!DOCTYPE html>\n<html>\n  <head>\n    <meta charset=\"UTF-8\">\n  </head>\n  <body>\n    <script src="https://cdn.polyfill.io/v2/polyfill.min.js?features=default,fetch"></script>\n    <script src=\"dist/bundle.js\"></script>\n  </body>\n</html>\n" >> index.html

touch webpack.config.js
echo -e "const HtmlWebpackPlugin = require('html-webpack-plugin');\nconst path = require('path');\n\nmodule.exports = {\n  mode: 'development',\n  entry: './src/index.js',\n  output: {\n    path: path.resolve(__dirname, './dist'),\n    filename: 'bundle.js',\n  },\n  plugins: [new HtmlWebpackPlugin()],\n};\n" >> webpack.config.js

mkdir src
touch src/index.js
echo "console.log(\"hello world\");" >> src/index.js
```

## Optional

jQuery
```
yarn add jquery
echo -e "import $ from 'jquery';\n$(document).ready(() => console.log('DOM is ready!'));" >> src/index.js
```


### Developing

Run local dev server:
```
webpack-dev-server
```

Production bundle
```
echo "dist" >> .gitignore # run once
webpack --mode production
```


### Commands
- ```npm start``` Starts the development server.
- ```npm run build``` Bundles the app into static files for production.
- ```npm test``` Starts the test runner.
- ```Ctrl+C``` Stops the development server.

# Generic Util Functions
