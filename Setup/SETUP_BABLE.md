[< back](./SETUP.md)

# Bable

## Packages

#### Core
```
npm i -D babel-core babel-preset-es2015
```
#### Presets
```
npm i -D babel-preset-es2015
```

#### CLI
```
npm i -D babel-cli
```

## Babelify NPM Script (needs CLI)
```
"babelify": "babel src/index.js --out-file build/bundle.js",
```

## .bablerc
```
{
  "presets": ["es2015"]
}
```