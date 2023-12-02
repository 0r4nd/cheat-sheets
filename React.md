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

### Start a new front-end project
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
git commit -m "Init repo with yarn"
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
