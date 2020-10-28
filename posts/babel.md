---
title: 'Babel'
date: '2020-01-02'
---

![Babel Logo.svg](/img/babel.png)


Es un compilador de _JavaScript,_ te permite usar el _JavaScript_ del futuro, **HOY.**

- [Babel.](https://babeljs.io/)
- [Learn ES Babel.](https://babeljs.io/docs/en/learn)
- [Using Babel.](https://babeljs.io/en/setup/)
- [CLI Tools.](https://babeljs.io/docs/en/babel-cli/)
- [Plugins Babel.](https://babeljs.io/docs/en/plugins/)

Instalación de paquetes:

    npm install -D babel-cli babel-core babel-preset-env

Crear el archivo de configuarción **`.babelrc`**

    { "presets": 
        [ "env" ], 
        "plugins": []
     }

Crear el _script_ necesario para compilar _ES_ con _Babel_ en el archivo **package.json**:

    { 
        "name": "taller-es", 
        "version": "1.0.0",
         "description": "Aprendiendo ECMAScript", 
         "main": "index.js", 
         "scripts": { 
             "es6": "babel src --watch --out-dir dist" 
         }, 
         "devDependencies": { 
             "babel-cli": "^6.24.1", 
             "babel-core": "^6.25.0", 
             "babel-preset-env": "^1.6.0" } 
         }

Ejecutar el _script_ en la terminal:

    npm run es6

