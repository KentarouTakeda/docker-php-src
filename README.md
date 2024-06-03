# docker-php-src

[php-src](https://github.com/php/php-src) development with Docker Compose and [VSCode Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## How to get started

*Make sure you have the Dev Containers extension installed in VSCode.*

1. Clone this project and open in VSCode
2. Select *Dev Containers: Reopen in Container* from the command palette
3. Obtaining and building source code as follows:

### Obtaining and building source code

When connecting to the container, the current directory is set to /home/build/php-src.
Then enter the following command:

```bash
# Obtain source code
git clone https://github.com/php/php-src.git ./

# Generate configure
./buildconf

# **For example:** configure the build settings as follows:
./configure \
  --enable-bcmath \
  --enable-calendar \
  --enable-dba \
  --enable-debug \
  --enable-dl-test=shared \
  --enable-exif \
  --enable-ftp \
  --enable-gd \
  --enable-mbstring \
  --enable-option-checking=fatal \
  --enable-pcntl \
  --enable-shmop \
  --enable-soap \
  --enable-sockets \
  --enable-sysvmsg \
  --enable-sysvsem \
  --enable-sysvshm \
  --enable-xmlreader \
  --enable-zend-test \
  --with-bz2 \
  --with-curl \
  --with-ffi \
  --with-freetype \
  --with-gettext \
  --with-gmp \
  --with-iconv \
  --with-jpeg \
  --with-libxml \
  --with-mhash \
  --with-mysqli=mysqlnd \
  --with-openssl \
  --with-pdo-firebird \
  --with-pdo-mysql=mysqlnd \
  --with-pdo-pgsql \
  --with-pdo-sqlite \
  --with-pgsql \
  --with-readline \
  --with-sodium \
  --with-tidy \
  --with-webp \
  --with-xsl \
  --with-zip \
  --with-zlib \

# Build the binaries
make -j$(nproc) 
```

## Remarks

* You can connect to PostgreSQL or MySQL by simply typing `psql` / `mysql`. No command line options are required.
* `./sapi/cli/` is set in PATH. Just run `php` and the binary you built will be executed.

## Contribution

I want to support as many extensions and libraries as possible.
If there is something that should be addressed on a priority basis,
please open an issue. Pull requests are also welcome.

## License

MIT
