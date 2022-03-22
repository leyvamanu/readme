# README PARA DESCARGAR
Clonamos el repositorio

    git clone https://github.com/leyvamanu/readme.git

Instalamos las dependencias PHP

    composer install

Instalamos las dependencias de JavaScript

    npm install

Arrancamos el servidor de symfony

    symfony server:start

Arrancamos el reload del navegador

    encore dev-server

# README PASOS A SEGUIDOS
Creamos el proyecto

    symfony new readme

Instalamos dependencias

Maker bundle
    
    composer require symfony/maker-bundle --dev

Profiler-pack

    composer require --dev symfony/profiler-pack

Dependencias basicas

    composer require doctrine/annotations

    composer require twig

    composer require symfony/webpack-encore-bundle

Creamos controlador

    symfony console make:controller IndexController

Instalamos dependencias npm

    npm install

Tailwind

    npm install

    npm install -D tailwindcss postcss autoprefixer

    npm install postcss-loader@^6.0.0 --save-dev

    npx tailwindcss init

Crear fichero postcss.config.js en la raiz del proyecto y añadir
    
    module.exports = {
      plugins: {
        tailwindcss: {},
        autoprefixer: {},
      },
    }

Añadir al fichero tailwind.config.js

    purge: [
        './templates/**/*.html.twig',
        './assets/**/*.css',
        './assets/**/*.js',
      ],

Añadir al fichero webpack.config.js
    
    //enablers PostCss
    .enablePostCssLoader()

    //LiveReload
    .configureDevServerOptions((options) => {
        options.liveReload = true;
        options.hot = true;
        options.watchFiles = [
            './templates/**/*',
            './src/**/*'
        ]
    })
