# README 
##PARA DESCARGAR
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

##PASOS A PASO
Creamos el proyecto

    symfony new readme

###Instalamos dependencias

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

##Tailwind
Instalamos tailwind

    npm install

    npm install -D tailwindcss postcss autoprefixer

    npm install postcss-loader@^6.0.0 --save-dev

    npx tailwindcss init

Añadir al fichero tailwind.config.js

    purge: [
        './templates/**/*.html.twig',
        './assets/**/*.css',
        './assets/**/*.js',
      ],

##POSTCSS
Crear fichero postcss.config.js en la raiz del proyecto y añadir
    
    module.exports = {
      plugins: {
        tailwindcss: {},
        autoprefixer: {},
      },
    }

##LIVE RELOAD
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

##BASE DE DATOS
Dependencias

    composer require orm

Confirurar .env

    DATABASE_URL="mysql://db_user:db_password@127.0.0.1:3306/db_name?serverVersion=5.7&charset=utf8mb4"

Crear BD
    
    php bin/console doctrine:database:create

##Seguridad
Dependencias  
  
    composer require symfony/security-bundle

Crear entidad usuario

    php bin/console make:user

Actualizar BD

    php bin/console make:migration
    php bin/console doctrine:migrations:migrate

Formulario de registro

    composer require symfonycasts/verify-email-bundle
    php bin/console make:registration-form

Email

    composer require symfonycasts/verify-email-bundle

Descomentar .env (MaiHog)

    MAILER_DSN=smtp://localhost

(OPCIONAL) gmail mailer
    
    composer require symfony/google-mailer 