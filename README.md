Select anidado o Select dependientes
======

Código del ejemplo de Select anidados o Select dependientes con KumbiaPHP 1.0RC, del manual: [Select anidado o select dependientes](https://www.kumbiaphp.com/blog/2017/11/17/select-anidado-o-select-dependientes/)

[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/henrystivens/dependent-select/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/henrystivens/dependent-select/?branch=master)

## Correr en Docker

Como prerequisito debe tener instalado Docker en el sistema operatvo: [Obtener Docker](https://www.docker.com/products/overview)

### 1. Correr mysql con datos externos y publicado

``
docker run --detach --name=mysql-dev --env="MYSQL_ROOT_PASSWORD=root" --volume /home/usuario/mysql/data:/var/lib/mysql --publish 6603:3306 mysql:5.7
``

Cambia el valor del parámetro --volume por el directorio que desees

### 2. Importar base de datos

Importar el archivo *default/app/config/sql/dependent-selects.sql*

### 3. Correr Apache + PHP 7

En la carpeta raíz de este proyecto correr:

``
docker-compose up -d --build
``

o simplemente...

``
docker-compose up -d
``

Mirar la web en **http://localhost:8183**

La opción ``--build``, es sólo para la primera vez o cuando se cambian los ficheros del docker.

``docker-compose up`` (muestra el log en la terminal)

``docker-compose up -d `` (como demonio, sin datos en la terminal)