[< back](./SETUP.md)

# Air BNB Linting

## Basic
#### Install
```
npm i -D eslint eslint-plugin-import eslint-config-airbnb-base
```
#### .eslintrc
```
{
    "env": {
        "browser": true,
        "es6": true,
        "node": true,
        "mocha": true
    },
    "extends": "airbnb-base",
    "plugins": [
        "import"
    ]
}
```

## React
#### Install
```
npm i -D eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-config-airbnb
```
#### .eslintrc
```
{
    "env": {
        "browser": true,
        "es6": true,
        "node": true,
        "mocha": true
    },
    "plugins": [
        "import"
    ],
    "extends": "airbnb",
    "parser": "babel-eslint",
    "rules": {  
        // react
        "react/prefer-es6-class": 0,
        "react/jsx-filename-extension": 0,
        "react/jsx-curly-spacing": [ 2, "always" ]
    }
}
```