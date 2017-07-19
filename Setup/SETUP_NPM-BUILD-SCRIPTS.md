### Static HTML Site
With bundlers, watchers and simple JS webpack
```
  "build": "npm install && npm run build-all",
  "build-all": "rimraf dist && npm run build-css && npm run build-html && npm run build-js",
  "build-html": "npm run build-html0 && npm run build-html1 && npm run build-html2",
  "build-html0": "html-partials-compiler ./src/index.html > ./dist/index.html",
  "build-html1": "htmlmin -o ./dist/index.min.html ./dist/index.html",
  "build-html2": "mv ./dist/index.min.html ./dist/index.html",
  "build-css": "node-sass --output-style compressed src/scss/main.scss dist/css/main.min.css",
  "build-js": "webpack --config webpack.config.js",
  "lint": "eslint src",
  "start": "npm run start-all",
  "start-all": "concurrently -n \"watch,node\" --prefix name \"npm run watch-all\" \"npm run start-server\"",
  "start-server": "node server",
  "test": "mocha --compilers js:babel-core/register src/**/*.test.js",
  "watch-all": "concurrently -n \"html,css,js\" --prefix name \"npm run watch-html\" \"npm run watch-css\" \"npm run watch-js\"",
  "watch-html": "nodemon -e html --ignore dist/ -x \"npm run build-html\"",
  "watch-css": "nodemon -e scss --ignore dist/ -x \"npm run build-css\"",
  "watch-js": "nodemon -e js --ignore dist/ -x \"npm run build-js\""
```