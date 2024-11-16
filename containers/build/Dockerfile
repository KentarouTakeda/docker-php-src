FROM ubuntu:latest

RUN apt update \
 && apt install -y --no-install-recommends \
    autoconf \
    bash-completion \
    bison \
    build-essential \
    ca-certificates \
    curl \
    firebird-dev \
    gcc \
    gdb \
    git \
    gnupg \
    jq \
    less \
    libbz2-dev \
    libcurl4-gnutls-dev \
    libffi-dev \
    libfreetype6-dev \
    libgmp-dev \
    libjpeg-dev \
    libkrb5-dev \
    libmysqlclient-dev \
    libonig-dev \
    libpng-dev \
    libpq-dev \
    libpspell-dev \
    libreadline-dev \
    libsodium-dev \
    libsqlite3-dev \
    libtidy-dev \
    libwebp-dev \
    libxml2-dev \
    libxslt1-dev \
    libzip-dev \
    make \
    mysql-client \
    netcat-openbsd \
    pkg-config \
    postgresql-client \
    re2c \
    ssh \
    sqlite3 \
    sudo \
    tree \
    unzip \
    vim \
    wget \
 && mkdir -p /etc/apt/keyrings \
 && curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg \
 && echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_20.x nodistro main" > /etc/apt/sources.list.d/nodesource.list \
 && curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg > /etc/apt/keyrings/githubcli-archive-keyring.gpg \
 && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" > /etc/apt/sources.list.d/github-cli.list \
 && apt update \
 && apt install  -y --no-install-recommends \
    gh  \
    nodejs  \
 && apt clean \
 && rm -rf /var/lib/apt/lists/* \
;

COPY sudoers /etc/sudoers.d/all

RUN adduser build
USER build
COPY gitignore /home/build/
RUN mkdir /home/build/php-src
WORKDIR /home/build/php-src
ENV PATH="${PATH}:/home/build/php-src/sapi/cli/"
CMD [ "bash" ]