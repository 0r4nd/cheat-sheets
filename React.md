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
add it if missing:
```
code ~/zshrc
```

### Create a new project
```
npx create-react-app MyApp
cd MyApp
```

### Add some packages
```
yarn add eslint --dev
eslint --init
git add .
git commit -m "Added ESLint"
```

### Commands
- ```npm start``` Starts the development server.
- ```npm run build``` Bundles the app into static files for production.
- ```npm test``` Starts the test runner.
- ```Ctrl+C``` Stops the development server.

# Generic Util Functions
