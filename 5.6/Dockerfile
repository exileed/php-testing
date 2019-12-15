FROM php:5.6-fpm-alpine

# Install dev dependencies
RUN apk add --no-cache --virtual .build-deps \
    $PHPIZE_DEPS \
    make \
    g++ \
    gcc \
    curl-dev \
    imagemagick-dev \
    oniguruma-dev \
    icu-dev \
    libtool \
    libxml2-dev \
    postgresql-dev \
    sqlite-dev \
    # Install production dependencies
 && apk add --no-cache \
    bash \
    curl \
    git \
    imagemagick \
    icu \
    libc-dev \
    libpng-dev \
    mysql-client \
    openssh-client \
    postgresql-libs \
    rsync \
    zlib-dev \
    libzip-dev

# Install PECL and PEAR extensions
RUN yes | pecl install \
    imagick \
    xdebug-2.5.5

# Install and enable php extensions
RUN docker-php-ext-enable \
    imagick \
    xdebug \
    && docker-php-ext-configure zip
RUN docker-php-ext-install \
    curl \
    iconv \
    mbstring \
    pdo \
    pdo_mysql \
    pdo_pgsql \
    pdo_sqlite \
    pcntl \
    tokenizer \
    xml \
    gd \
    bcmath \
    sockets \
    intl \
    && apk del \
    .build-deps

RUN curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer \
    && rm -rf /var/cache/apk/*