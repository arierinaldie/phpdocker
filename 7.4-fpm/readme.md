## phpdocker:7.4-fpm
extended from php:7.4-fpm image
* run `docker build -t xamarie/phpdocker:7.4-fpm .` to build.
* run `docker push xamarie/phpdocker:7.4-fpm` to push.
* run `docker pull xamarie/phpdocker:7.4-fpm` to pull/use
* run `docker run -it --rm --name testrun_phpdocker xamarie/phpdocker:7.4-fpm bash` to test run after build or.
* run `docker run -it --rm --name testrun_phpdocker --user root xamarie/phpdocker:7.4-fpm bash` to test run as root.