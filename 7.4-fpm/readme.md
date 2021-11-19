## phpdocker:7.4-fpm
extended from php:7.4-fpm image
* run `docker build -t xamarie/phpdocker:7.4-fpm .` to build.
* run `docker push xamarie/phpdocker:7.4-fpm` to push.
* run `docker pull xamarie/phpdocker:7.4-fpm` to pull/use
* run `docker run --rm --name testrun_phpdocker xamarie/phpdocker:7.4-fpm` to test run after build, and use `docker exec -it testrun_phpdocker sh` to interact with it. you can stop it with `docker stop testrun_phpdocker` when its done.