[< back](./SETUP.md)

# Node SASS

#### Install
```
npm i -D node-sass-chokidar nodemon
```

## NPM Scripts

#### Single File
```
"build-css": "node-sass-chokidar --include-path scss",
"watch-css": "nodemon -e scss -x \"npm run build-css\"",
```
#### Recursive
```
"build-css": "node-sass-chokidar --recursive src/ -o src/",
"watch-css": "nodemon -e scss -x \"npm run build-css\"",
```