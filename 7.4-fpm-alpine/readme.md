## phpdocker:7.4-fpm-alpine
extended from php:7.4-fpm-alpine3.11 image
* run `docker build -t xamarie/phpdocker:7.4-fpm-alpine .` to build.
* run `docker push xamarie/phpdocker:7.4-fpm-alpine` to push.
* run `docker pull xamarie/phpdocker:7.4-fpm-alpine` to pull/use.
* run `docker run --rm --name testrun_phpdocker xamarie/phpdocker:7.4-fpm-alpine` to test run after build, and use `docker exec -it testrun_phpdocker sh` to interact with it. you can stop it with `docker stop testrun_phpdocker` when its done.