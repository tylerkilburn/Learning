[< back](./SETUP.md)

# Air BNB Linting

#### Install
```
npm i -D eslint eslint-plugin-import eslint-config-airbnb
```

#### Simple .eslintrc
```
{
    "extends": "airbnb",
    "plugins": [
        "import"
    ]
}
```

#### React Ready .eslintrc
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