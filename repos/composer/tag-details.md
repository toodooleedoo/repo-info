<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `composer`

-	[`composer:1.4.2`](#composer142)
-	[`composer:1.4`](#composer14)
-	[`composer:1`](#composer1)
-	[`composer:latest`](#composerlatest)
-	[`composer:1.3.3`](#composer133)
-	[`composer:1.3`](#composer13)

## `composer:1.4.2`

```console
$ docker pull composer@sha256:c0ea52c37c79ea586ce5a6254eb73f43006a1cfe3c2e2488680f1258a6d2356e
```

-	Platforms:
	-	linux; amd64

### `composer:1.4.2` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **55.9 MB (55891143 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cb2368eb833901da9326a99a72ef7a54c5feda91172e842bf1140f925ccac205`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Sat, 13 May 2017 00:05:35 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Sat, 13 May 2017 00:05:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Sat, 13 May 2017 00:05:43 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Sat, 13 May 2017 00:05:43 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Sat, 13 May 2017 00:05:45 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Sat, 13 May 2017 00:05:45 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:46 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:47 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Sat, 13 May 2017 00:05:48 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Sat, 13 May 2017 00:05:48 GMT
ENV PHP_VERSION=7.1.5
# Sat, 13 May 2017 00:05:49 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.5.tar.xz.asc/from/this/mirror
# Sat, 13 May 2017 00:05:50 GMT
ENV PHP_SHA256=d149a3c396c45611f5dc6bf14be190f464897145a76a8e5851cf18ff7094f6ac PHP_MD5=fb0702321c7aceac68c82b8c7a10d196
# Sat, 13 May 2017 00:05:58 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 13 May 2017 00:05:59 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 13 May 2017 00:09:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps
# Sat, 13 May 2017 00:10:01 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Sat, 13 May 2017 00:10:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 13 May 2017 00:10:03 GMT
CMD ["php" "-a"]
# Sat, 13 May 2017 03:07:06 GMT
RUN apk --no-cache add curl git subversion openssh openssl mercurial tini bash
# Sat, 13 May 2017 03:07:07 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 13 May 2017 03:07:08 GMT
ENV PATH=/composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_HOME=/composer
# Wed, 17 May 2017 18:03:36 GMT
ENV COMPOSER_VERSION=1.4.2
# Wed, 17 May 2017 18:03:41 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/da290238de6d63faace0343efbdd5aa9354332c5/web/installer  && php -r "     \$signature = '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && rm /tmp/installer.php  && composer --ansi --version --no-interaction
# Wed, 17 May 2017 18:03:42 GMT
COPY file:0b943ec33b364492b10e7a774becd40d3fec03eb7db67cc0528769b329117e32 in /docker-entrypoint.sh 
# Wed, 17 May 2017 18:03:43 GMT
WORKDIR /app
# Wed, 17 May 2017 18:03:44 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 17 May 2017 18:03:45 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f0bf25c22e185588f5556af1e7b9d67bdc2879f6173fd516350f73a2deb29f`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 1.1 MB (1081302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80549166a18f9060850abdc57136a60481cb83b1fa5dd7b8816907cb5bb7b611`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03a30cf12edf726e91cf3093d0c7aa86497903a99d4b0aca5589b746aeffeed3`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:454d83b3ec8bf2492b1dcfb1864ad45873ed18824c1cadf7a20a487ce6cc7e25`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 13.0 MB (12971389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cebfa4d6a80c726a84f89ef6bd6a95db22a2b6dd95c82d4f49be3c7c493f3f86`  
		Last Modified: Sat, 13 May 2017 01:40:33 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a5fcabde13864e80ffd3bff5f6c0a67b793043e7ff5c40a8d46326ffc371dd3`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 10.7 MB (10700912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c5bd13d24c81560810a7af37c19d557ca5fa17dd3bc9e39b01443330b52a96`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91c9048a337eb793767f4f1ef1ac80e875b6d2ec23992fed51262f4ea0cb1229`  
		Last Modified: Sat, 13 May 2017 03:08:14 GMT  
		Size: 28.3 MB (28260106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8790836622ab48604c74bdef1de164b2d7cd2cea1fe0d964d92cc4af91a5f2e`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 268.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb0b55ecc13e2c0d21d4a657fcafc130545f0e01df5f68975d95420ef7b37ba4`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 489.5 KB (489474 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de208c7f12391552cca710d8ec4353a3f5b55e250c0df2450e6f48b0b4d79ddb`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 528.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63f3d8f4556e2560c5f2a5b5ec59b17da9be4ad47071486c0a726f6c4d8bb548`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.4`

```console
$ docker pull composer@sha256:c0ea52c37c79ea586ce5a6254eb73f43006a1cfe3c2e2488680f1258a6d2356e
```

-	Platforms:
	-	linux; amd64

### `composer:1.4` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **55.9 MB (55891143 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cb2368eb833901da9326a99a72ef7a54c5feda91172e842bf1140f925ccac205`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Sat, 13 May 2017 00:05:35 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Sat, 13 May 2017 00:05:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Sat, 13 May 2017 00:05:43 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Sat, 13 May 2017 00:05:43 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Sat, 13 May 2017 00:05:45 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Sat, 13 May 2017 00:05:45 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:46 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:47 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Sat, 13 May 2017 00:05:48 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Sat, 13 May 2017 00:05:48 GMT
ENV PHP_VERSION=7.1.5
# Sat, 13 May 2017 00:05:49 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.5.tar.xz.asc/from/this/mirror
# Sat, 13 May 2017 00:05:50 GMT
ENV PHP_SHA256=d149a3c396c45611f5dc6bf14be190f464897145a76a8e5851cf18ff7094f6ac PHP_MD5=fb0702321c7aceac68c82b8c7a10d196
# Sat, 13 May 2017 00:05:58 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 13 May 2017 00:05:59 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 13 May 2017 00:09:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps
# Sat, 13 May 2017 00:10:01 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Sat, 13 May 2017 00:10:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 13 May 2017 00:10:03 GMT
CMD ["php" "-a"]
# Sat, 13 May 2017 03:07:06 GMT
RUN apk --no-cache add curl git subversion openssh openssl mercurial tini bash
# Sat, 13 May 2017 03:07:07 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 13 May 2017 03:07:08 GMT
ENV PATH=/composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_HOME=/composer
# Wed, 17 May 2017 18:03:36 GMT
ENV COMPOSER_VERSION=1.4.2
# Wed, 17 May 2017 18:03:41 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/da290238de6d63faace0343efbdd5aa9354332c5/web/installer  && php -r "     \$signature = '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && rm /tmp/installer.php  && composer --ansi --version --no-interaction
# Wed, 17 May 2017 18:03:42 GMT
COPY file:0b943ec33b364492b10e7a774becd40d3fec03eb7db67cc0528769b329117e32 in /docker-entrypoint.sh 
# Wed, 17 May 2017 18:03:43 GMT
WORKDIR /app
# Wed, 17 May 2017 18:03:44 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 17 May 2017 18:03:45 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f0bf25c22e185588f5556af1e7b9d67bdc2879f6173fd516350f73a2deb29f`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 1.1 MB (1081302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80549166a18f9060850abdc57136a60481cb83b1fa5dd7b8816907cb5bb7b611`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03a30cf12edf726e91cf3093d0c7aa86497903a99d4b0aca5589b746aeffeed3`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:454d83b3ec8bf2492b1dcfb1864ad45873ed18824c1cadf7a20a487ce6cc7e25`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 13.0 MB (12971389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cebfa4d6a80c726a84f89ef6bd6a95db22a2b6dd95c82d4f49be3c7c493f3f86`  
		Last Modified: Sat, 13 May 2017 01:40:33 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a5fcabde13864e80ffd3bff5f6c0a67b793043e7ff5c40a8d46326ffc371dd3`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 10.7 MB (10700912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c5bd13d24c81560810a7af37c19d557ca5fa17dd3bc9e39b01443330b52a96`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91c9048a337eb793767f4f1ef1ac80e875b6d2ec23992fed51262f4ea0cb1229`  
		Last Modified: Sat, 13 May 2017 03:08:14 GMT  
		Size: 28.3 MB (28260106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8790836622ab48604c74bdef1de164b2d7cd2cea1fe0d964d92cc4af91a5f2e`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 268.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb0b55ecc13e2c0d21d4a657fcafc130545f0e01df5f68975d95420ef7b37ba4`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 489.5 KB (489474 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de208c7f12391552cca710d8ec4353a3f5b55e250c0df2450e6f48b0b4d79ddb`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 528.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63f3d8f4556e2560c5f2a5b5ec59b17da9be4ad47071486c0a726f6c4d8bb548`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1`

```console
$ docker pull composer@sha256:c0ea52c37c79ea586ce5a6254eb73f43006a1cfe3c2e2488680f1258a6d2356e
```

-	Platforms:
	-	linux; amd64

### `composer:1` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **55.9 MB (55891143 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cb2368eb833901da9326a99a72ef7a54c5feda91172e842bf1140f925ccac205`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Sat, 13 May 2017 00:05:35 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Sat, 13 May 2017 00:05:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Sat, 13 May 2017 00:05:43 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Sat, 13 May 2017 00:05:43 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Sat, 13 May 2017 00:05:45 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Sat, 13 May 2017 00:05:45 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:46 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:47 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Sat, 13 May 2017 00:05:48 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Sat, 13 May 2017 00:05:48 GMT
ENV PHP_VERSION=7.1.5
# Sat, 13 May 2017 00:05:49 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.5.tar.xz.asc/from/this/mirror
# Sat, 13 May 2017 00:05:50 GMT
ENV PHP_SHA256=d149a3c396c45611f5dc6bf14be190f464897145a76a8e5851cf18ff7094f6ac PHP_MD5=fb0702321c7aceac68c82b8c7a10d196
# Sat, 13 May 2017 00:05:58 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 13 May 2017 00:05:59 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 13 May 2017 00:09:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps
# Sat, 13 May 2017 00:10:01 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Sat, 13 May 2017 00:10:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 13 May 2017 00:10:03 GMT
CMD ["php" "-a"]
# Sat, 13 May 2017 03:07:06 GMT
RUN apk --no-cache add curl git subversion openssh openssl mercurial tini bash
# Sat, 13 May 2017 03:07:07 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 13 May 2017 03:07:08 GMT
ENV PATH=/composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_HOME=/composer
# Wed, 17 May 2017 18:03:36 GMT
ENV COMPOSER_VERSION=1.4.2
# Wed, 17 May 2017 18:03:41 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/da290238de6d63faace0343efbdd5aa9354332c5/web/installer  && php -r "     \$signature = '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && rm /tmp/installer.php  && composer --ansi --version --no-interaction
# Wed, 17 May 2017 18:03:42 GMT
COPY file:0b943ec33b364492b10e7a774becd40d3fec03eb7db67cc0528769b329117e32 in /docker-entrypoint.sh 
# Wed, 17 May 2017 18:03:43 GMT
WORKDIR /app
# Wed, 17 May 2017 18:03:44 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 17 May 2017 18:03:45 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f0bf25c22e185588f5556af1e7b9d67bdc2879f6173fd516350f73a2deb29f`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 1.1 MB (1081302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80549166a18f9060850abdc57136a60481cb83b1fa5dd7b8816907cb5bb7b611`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03a30cf12edf726e91cf3093d0c7aa86497903a99d4b0aca5589b746aeffeed3`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:454d83b3ec8bf2492b1dcfb1864ad45873ed18824c1cadf7a20a487ce6cc7e25`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 13.0 MB (12971389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cebfa4d6a80c726a84f89ef6bd6a95db22a2b6dd95c82d4f49be3c7c493f3f86`  
		Last Modified: Sat, 13 May 2017 01:40:33 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a5fcabde13864e80ffd3bff5f6c0a67b793043e7ff5c40a8d46326ffc371dd3`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 10.7 MB (10700912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c5bd13d24c81560810a7af37c19d557ca5fa17dd3bc9e39b01443330b52a96`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91c9048a337eb793767f4f1ef1ac80e875b6d2ec23992fed51262f4ea0cb1229`  
		Last Modified: Sat, 13 May 2017 03:08:14 GMT  
		Size: 28.3 MB (28260106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8790836622ab48604c74bdef1de164b2d7cd2cea1fe0d964d92cc4af91a5f2e`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 268.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb0b55ecc13e2c0d21d4a657fcafc130545f0e01df5f68975d95420ef7b37ba4`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 489.5 KB (489474 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de208c7f12391552cca710d8ec4353a3f5b55e250c0df2450e6f48b0b4d79ddb`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 528.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63f3d8f4556e2560c5f2a5b5ec59b17da9be4ad47071486c0a726f6c4d8bb548`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:latest`

```console
$ docker pull composer@sha256:c0ea52c37c79ea586ce5a6254eb73f43006a1cfe3c2e2488680f1258a6d2356e
```

-	Platforms:
	-	linux; amd64

### `composer:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **55.9 MB (55891143 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:cb2368eb833901da9326a99a72ef7a54c5feda91172e842bf1140f925ccac205`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Sat, 13 May 2017 00:05:35 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Sat, 13 May 2017 00:05:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Sat, 13 May 2017 00:05:43 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Sat, 13 May 2017 00:05:43 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Sat, 13 May 2017 00:05:45 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Sat, 13 May 2017 00:05:45 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:46 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:47 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Sat, 13 May 2017 00:05:48 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Sat, 13 May 2017 00:05:48 GMT
ENV PHP_VERSION=7.1.5
# Sat, 13 May 2017 00:05:49 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.5.tar.xz.asc/from/this/mirror
# Sat, 13 May 2017 00:05:50 GMT
ENV PHP_SHA256=d149a3c396c45611f5dc6bf14be190f464897145a76a8e5851cf18ff7094f6ac PHP_MD5=fb0702321c7aceac68c82b8c7a10d196
# Sat, 13 May 2017 00:05:58 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 13 May 2017 00:05:59 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 13 May 2017 00:09:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps
# Sat, 13 May 2017 00:10:01 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Sat, 13 May 2017 00:10:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 13 May 2017 00:10:03 GMT
CMD ["php" "-a"]
# Sat, 13 May 2017 03:07:06 GMT
RUN apk --no-cache add curl git subversion openssh openssl mercurial tini bash
# Sat, 13 May 2017 03:07:07 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 13 May 2017 03:07:08 GMT
ENV PATH=/composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_HOME=/composer
# Wed, 17 May 2017 18:03:36 GMT
ENV COMPOSER_VERSION=1.4.2
# Wed, 17 May 2017 18:03:41 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/da290238de6d63faace0343efbdd5aa9354332c5/web/installer  && php -r "     \$signature = '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && rm /tmp/installer.php  && composer --ansi --version --no-interaction
# Wed, 17 May 2017 18:03:42 GMT
COPY file:0b943ec33b364492b10e7a774becd40d3fec03eb7db67cc0528769b329117e32 in /docker-entrypoint.sh 
# Wed, 17 May 2017 18:03:43 GMT
WORKDIR /app
# Wed, 17 May 2017 18:03:44 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 17 May 2017 18:03:45 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f0bf25c22e185588f5556af1e7b9d67bdc2879f6173fd516350f73a2deb29f`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 1.1 MB (1081302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80549166a18f9060850abdc57136a60481cb83b1fa5dd7b8816907cb5bb7b611`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03a30cf12edf726e91cf3093d0c7aa86497903a99d4b0aca5589b746aeffeed3`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:454d83b3ec8bf2492b1dcfb1864ad45873ed18824c1cadf7a20a487ce6cc7e25`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 13.0 MB (12971389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cebfa4d6a80c726a84f89ef6bd6a95db22a2b6dd95c82d4f49be3c7c493f3f86`  
		Last Modified: Sat, 13 May 2017 01:40:33 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a5fcabde13864e80ffd3bff5f6c0a67b793043e7ff5c40a8d46326ffc371dd3`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 10.7 MB (10700912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c5bd13d24c81560810a7af37c19d557ca5fa17dd3bc9e39b01443330b52a96`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91c9048a337eb793767f4f1ef1ac80e875b6d2ec23992fed51262f4ea0cb1229`  
		Last Modified: Sat, 13 May 2017 03:08:14 GMT  
		Size: 28.3 MB (28260106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8790836622ab48604c74bdef1de164b2d7cd2cea1fe0d964d92cc4af91a5f2e`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 268.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb0b55ecc13e2c0d21d4a657fcafc130545f0e01df5f68975d95420ef7b37ba4`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 489.5 KB (489474 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de208c7f12391552cca710d8ec4353a3f5b55e250c0df2450e6f48b0b4d79ddb`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 528.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63f3d8f4556e2560c5f2a5b5ec59b17da9be4ad47071486c0a726f6c4d8bb548`  
		Last Modified: Wed, 17 May 2017 18:04:09 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.3.3`

```console
$ docker pull composer@sha256:81f1caf3e1ce913af9671eb98fd073ac6884497a96c78c6743b74bb27ad06333
```

-	Platforms:
	-	linux; amd64

### `composer:1.3.3` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **55.9 MB (55889110 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b7b12b426534433bb0519bfb9948841c88862cf9a05f5f26b82a3f32b0e9f4b6`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Sat, 13 May 2017 00:05:35 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Sat, 13 May 2017 00:05:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Sat, 13 May 2017 00:05:43 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Sat, 13 May 2017 00:05:43 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Sat, 13 May 2017 00:05:45 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Sat, 13 May 2017 00:05:45 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:46 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:47 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Sat, 13 May 2017 00:05:48 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Sat, 13 May 2017 00:05:48 GMT
ENV PHP_VERSION=7.1.5
# Sat, 13 May 2017 00:05:49 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.5.tar.xz.asc/from/this/mirror
# Sat, 13 May 2017 00:05:50 GMT
ENV PHP_SHA256=d149a3c396c45611f5dc6bf14be190f464897145a76a8e5851cf18ff7094f6ac PHP_MD5=fb0702321c7aceac68c82b8c7a10d196
# Sat, 13 May 2017 00:05:58 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 13 May 2017 00:05:59 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 13 May 2017 00:09:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps
# Sat, 13 May 2017 00:10:01 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Sat, 13 May 2017 00:10:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 13 May 2017 00:10:03 GMT
CMD ["php" "-a"]
# Sat, 13 May 2017 03:07:06 GMT
RUN apk --no-cache add curl git subversion openssh openssl mercurial tini bash
# Sat, 13 May 2017 03:07:07 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 13 May 2017 03:07:08 GMT
ENV PATH=/composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_HOME=/composer
# Sat, 13 May 2017 03:07:10 GMT
ENV COMPOSER_VERSION=1.3.3
# Sat, 13 May 2017 03:07:14 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/da290238de6d63faace0343efbdd5aa9354332c5/web/installer  && php -r "     \$signature = '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && rm /tmp/installer.php  && composer --ansi --version --no-interaction
# Sat, 13 May 2017 03:07:15 GMT
COPY file:0b943ec33b364492b10e7a774becd40d3fec03eb7db67cc0528769b329117e32 in /docker-entrypoint.sh 
# Sat, 13 May 2017 03:07:16 GMT
WORKDIR /app
# Sat, 13 May 2017 03:07:16 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 13 May 2017 03:07:17 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f0bf25c22e185588f5556af1e7b9d67bdc2879f6173fd516350f73a2deb29f`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 1.1 MB (1081302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80549166a18f9060850abdc57136a60481cb83b1fa5dd7b8816907cb5bb7b611`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03a30cf12edf726e91cf3093d0c7aa86497903a99d4b0aca5589b746aeffeed3`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:454d83b3ec8bf2492b1dcfb1864ad45873ed18824c1cadf7a20a487ce6cc7e25`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 13.0 MB (12971389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cebfa4d6a80c726a84f89ef6bd6a95db22a2b6dd95c82d4f49be3c7c493f3f86`  
		Last Modified: Sat, 13 May 2017 01:40:33 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a5fcabde13864e80ffd3bff5f6c0a67b793043e7ff5c40a8d46326ffc371dd3`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 10.7 MB (10700912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c5bd13d24c81560810a7af37c19d557ca5fa17dd3bc9e39b01443330b52a96`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91c9048a337eb793767f4f1ef1ac80e875b6d2ec23992fed51262f4ea0cb1229`  
		Last Modified: Sat, 13 May 2017 03:08:14 GMT  
		Size: 28.3 MB (28260106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8790836622ab48604c74bdef1de164b2d7cd2cea1fe0d964d92cc4af91a5f2e`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 268.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c66a3001a1e0ecfc86f38930f9466242a93713f5ba992698c279550eca4e506f`  
		Last Modified: Sat, 13 May 2017 03:08:09 GMT  
		Size: 487.4 KB (487439 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5e0db31cd355625025ba545cfa40f247143abdd9cc09451c03a2c3e72b59f49`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 530.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:267948e9adde05de694401b9350e1fb98bf94bb178d0576d65656b8382d87715`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `composer:1.3`

```console
$ docker pull composer@sha256:81f1caf3e1ce913af9671eb98fd073ac6884497a96c78c6743b74bb27ad06333
```

-	Platforms:
	-	linux; amd64

### `composer:1.3` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **55.9 MB (55889110 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b7b12b426534433bb0519bfb9948841c88862cf9a05f5f26b82a3f32b0e9f4b6`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["composer"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Sat, 13 May 2017 00:05:35 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Sat, 13 May 2017 00:05:40 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Sat, 13 May 2017 00:05:43 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Sat, 13 May 2017 00:05:43 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Sat, 13 May 2017 00:05:45 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Sat, 13 May 2017 00:05:45 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:46 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Sat, 13 May 2017 00:05:47 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Sat, 13 May 2017 00:05:48 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Sat, 13 May 2017 00:05:48 GMT
ENV PHP_VERSION=7.1.5
# Sat, 13 May 2017 00:05:49 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.5.tar.xz.asc/from/this/mirror
# Sat, 13 May 2017 00:05:50 GMT
ENV PHP_SHA256=d149a3c396c45611f5dc6bf14be190f464897145a76a8e5851cf18ff7094f6ac PHP_MD5=fb0702321c7aceac68c82b8c7a10d196
# Sat, 13 May 2017 00:05:58 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Sat, 13 May 2017 00:05:59 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 13 May 2017 00:09:59 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps
# Sat, 13 May 2017 00:10:01 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Sat, 13 May 2017 00:10:02 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 13 May 2017 00:10:03 GMT
CMD ["php" "-a"]
# Sat, 13 May 2017 03:07:06 GMT
RUN apk --no-cache add curl git subversion openssh openssl mercurial tini bash
# Sat, 13 May 2017 03:07:07 GMT
RUN echo "memory_limit=-1" > "$PHP_INI_DIR/conf.d/memory-limit.ini"  && echo "date.timezone=${PHP_TIMEZONE:-UTC}" > "$PHP_INI_DIR/conf.d/date_timezone.ini"
# Sat, 13 May 2017 03:07:08 GMT
ENV PATH=/composer/vendor/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_ALLOW_SUPERUSER=1
# Sat, 13 May 2017 03:07:09 GMT
ENV COMPOSER_HOME=/composer
# Sat, 13 May 2017 03:07:10 GMT
ENV COMPOSER_VERSION=1.3.3
# Sat, 13 May 2017 03:07:14 GMT
RUN curl -s -f -L -o /tmp/installer.php https://raw.githubusercontent.com/composer/getcomposer.org/da290238de6d63faace0343efbdd5aa9354332c5/web/installer  && php -r "     \$signature = '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410';     \$hash = hash('SHA384', file_get_contents('/tmp/installer.php'));     if (!hash_equals(\$signature, \$hash)) {         unlink('/tmp/installer.php');         echo 'Integrity check failed, installer is either corrupt or worse.' . PHP_EOL;         exit(1);     }"  && php /tmp/installer.php --no-ansi --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}  && rm /tmp/installer.php  && composer --ansi --version --no-interaction
# Sat, 13 May 2017 03:07:15 GMT
COPY file:0b943ec33b364492b10e7a774becd40d3fec03eb7db67cc0528769b329117e32 in /docker-entrypoint.sh 
# Sat, 13 May 2017 03:07:16 GMT
WORKDIR /app
# Sat, 13 May 2017 03:07:16 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 13 May 2017 03:07:17 GMT
CMD ["composer"]
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9f0bf25c22e185588f5556af1e7b9d67bdc2879f6173fd516350f73a2deb29f`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 1.1 MB (1081302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80549166a18f9060850abdc57136a60481cb83b1fa5dd7b8816907cb5bb7b611`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03a30cf12edf726e91cf3093d0c7aa86497903a99d4b0aca5589b746aeffeed3`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:454d83b3ec8bf2492b1dcfb1864ad45873ed18824c1cadf7a20a487ce6cc7e25`  
		Last Modified: Sat, 13 May 2017 01:40:34 GMT  
		Size: 13.0 MB (12971389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cebfa4d6a80c726a84f89ef6bd6a95db22a2b6dd95c82d4f49be3c7c493f3f86`  
		Last Modified: Sat, 13 May 2017 01:40:33 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a5fcabde13864e80ffd3bff5f6c0a67b793043e7ff5c40a8d46326ffc371dd3`  
		Last Modified: Sat, 13 May 2017 01:40:36 GMT  
		Size: 10.7 MB (10700912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e7c5bd13d24c81560810a7af37c19d557ca5fa17dd3bc9e39b01443330b52a96`  
		Last Modified: Sat, 13 May 2017 01:40:32 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:91c9048a337eb793767f4f1ef1ac80e875b6d2ec23992fed51262f4ea0cb1229`  
		Last Modified: Sat, 13 May 2017 03:08:14 GMT  
		Size: 28.3 MB (28260106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8790836622ab48604c74bdef1de164b2d7cd2cea1fe0d964d92cc4af91a5f2e`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 268.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c66a3001a1e0ecfc86f38930f9466242a93713f5ba992698c279550eca4e506f`  
		Last Modified: Sat, 13 May 2017 03:08:09 GMT  
		Size: 487.4 KB (487439 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e5e0db31cd355625025ba545cfa40f247143abdd9cc09451c03a2c3e72b59f49`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 530.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:267948e9adde05de694401b9350e1fb98bf94bb178d0576d65656b8382d87715`  
		Last Modified: Sat, 13 May 2017 03:08:08 GMT  
		Size: 92.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
