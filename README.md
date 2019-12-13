<p align="center">
    <a href="https://www.docker.com/" target="_blank">
        <img src="https://www.docker.com/sites/default/files/mono_vertical_large.png" height="100px">
    </a>
    <h1 align="center">Docker image for testing (CI)</h1>
    <br>
</p>

**Stable** 
[![pipeline status](https://gitlab.com/yiisoft/yii2-docker/badges/master/pipeline.svg)](https://gitlab.com/yiisoft/yii2-docker/commits/master)


## About

These Docker images are built on top of the official PHP Docker image (alpine), they contain additional PHP extensions required to testing (CI, but no code of the framework itself.
The `Dockerfile`(s) of this repository are designed to build from different PHP-versions by using *build arguments*.

### Available versions for `exileed/php-testing`

```
7.4, 7.3, 7.2, 7.0, 5.6 
```


### Available extensions

```
curl
iconv
mbstring
pdo
pdo_mysql
pdo_pgsql
pdo_sqlite
pcntl
tokenizer
xml
gd
bcmath
sockets
intl
imagick
xdebug
zip

```


### Example build

`docker build -t exileed/php-testing:5.6 --build-arg PHP_BASE_IMAGE_VERSION=7.3 .`