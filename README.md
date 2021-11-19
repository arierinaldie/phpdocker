## [xamarie/phpdocker](https://github.com/xamarie/phpdocker)

This is the Git repo for `xamarie/phpdocker`, preinstalled php based extention to run or develope application using php. This image based on official [`php`](https://hub.docker.com/_/php/). See [the Docker Hub page](https://hub.docker.com/_/php/) for any official references.

for every image in this repo, it already contains:
* php ext installed:
    - exif 
    - pdo 
    - pdo_mysql 
    - mysqli 
    - pdo_pgsql 
    - pgsql 
    - bcmath 
    - ctype 
    - fileinfo 
    - json 
    - mbstring 
    - tokenizer 
    - opcache
    - zip 
    - intl 
    - xml 
    - dom 
    - xmlrpc 
    - xmlwriter 
    - gd 
    - sockets
    - iconv
    - curl
    - igbinary
    - redis
    - apcu
* additional
    - composer
    - supervisord
    - git
    - openssh
    - nano 
    - zip 
    - unzip 
    - wget

this repo is open for all to contribute to make php image better, stable and ready to use. please use the `main` branch as a base to create a new branch for the new image. all images that have been successfully developed and tested can be merge to `master`.

All `xamarie/php` images available at [docker hub](https://hub.docker.com/r/xamarie/php/tags).
