## `redmine:3-passenger`

```console
$ docker pull redmine@sha256:2bed3355a205cc5733d82828e38eb92e09393f9426e3cf3727d73dc3c8626167
```

-	Platforms:
	-	linux; amd64

### `redmine:3-passenger` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **269.8 MB (269785715 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:00df94c1561aa56daac335bf25aed464f679758614a5385a74c39d242622a47c`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Wed, 10 May 2017 15:53:10 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 15:53:12 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Wed, 10 May 2017 16:00:06 GMT
ENV RUBY_MAJOR=2.2
# Wed, 10 May 2017 16:00:06 GMT
ENV RUBY_VERSION=2.2.7
# Wed, 10 May 2017 16:00:07 GMT
ENV RUBY_DOWNLOAD_SHA256=234c8aee6543da9efd67008e6e7ee740d41ed57a52e797f65043c3b5ec3bcb53
# Wed, 10 May 2017 16:00:08 GMT
ENV RUBYGEMS_VERSION=2.6.12
# Thu, 11 May 2017 18:47:33 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Thu, 11 May 2017 18:47:34 GMT
ENV BUNDLER_VERSION=1.14.6
# Thu, 11 May 2017 18:47:36 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Thu, 11 May 2017 18:47:37 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 11 May 2017 18:47:38 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 11 May 2017 18:47:39 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 11 May 2017 18:47:41 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Thu, 11 May 2017 18:47:42 GMT
CMD ["irb"]
# Thu, 11 May 2017 19:44:05 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Thu, 11 May 2017 19:44:17 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 11 May 2017 19:44:18 GMT
ENV GOSU_VERSION=1.7
# Thu, 11 May 2017 19:44:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Thu, 11 May 2017 19:44:25 GMT
ENV TINI_VERSION=v0.9.0
# Thu, 11 May 2017 19:44:28 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini.asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 11 May 2017 19:45:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		imagemagick 		libmysqlclient18 		libpq5 		libsqlite3-0 				bzr 		git 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 11 May 2017 19:45:17 GMT
ENV RAILS_ENV=production
# Thu, 11 May 2017 19:45:19 GMT
WORKDIR /usr/src/redmine
# Thu, 11 May 2017 21:21:01 GMT
ENV REDMINE_VERSION=3.3.3
# Thu, 11 May 2017 21:21:02 GMT
ENV REDMINE_DOWNLOAD_MD5=c946839c9a51dba48ae7c34c5351f677
# Thu, 11 May 2017 21:21:06 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 11 May 2017 21:23:29 GMT
RUN buildDeps=' 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	' 	&& set -ex 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends 	&& rm -rf /var/lib/apt/lists/* 	&& bundle install --without development test 	&& for adapter in mysql2 postgresql sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 	done 	&& rm ./config/database.yml 	&& apt-get purge -y --auto-remove $buildDeps
# Thu, 11 May 2017 21:23:30 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 11 May 2017 21:23:31 GMT
COPY file:5efb6ca648b54af01740423ca0fdde905eae0ce732d8f2683c79dcf93e0e86c5 in / 
# Thu, 11 May 2017 21:23:31 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 11 May 2017 21:23:32 GMT
EXPOSE 3000/tcp
# Thu, 11 May 2017 21:23:33 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Mon, 15 May 2017 21:49:18 GMT
ENV PASSENGER_VERSION=5.1.4
# Mon, 15 May 2017 21:49:36 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Mon, 15 May 2017 21:49:38 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Mon, 15 May 2017 21:49:38 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0aaa89427703d5bdd37a7b3c98c01a6e0434e2906c7212919ed6277622bf9abb`  
		Last Modified: Thu, 11 May 2017 19:23:22 GMT  
		Size: 10.2 MB (10159984 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e4351445696bc2482da72ce5d84caf70003361f2997c9b7e2adae06a3725118`  
		Last Modified: Thu, 11 May 2017 19:23:19 GMT  
		Size: 201.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72c399ee88adc9c41869a4d43d7adf200cd366d681b8a37e8496ce79f80a14b2`  
		Last Modified: Thu, 11 May 2017 19:27:58 GMT  
		Size: 33.8 MB (33805598 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f5ccd387319782eeaddcf31a8eeeb50455c70fd4b17cf692d026dc03b28d9ea`  
		Last Modified: Thu, 11 May 2017 19:27:45 GMT  
		Size: 639.5 KB (639471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2c40912eb7260242149274ddcd3239d42ec8deba28d6ca6829cf6673f7bc6c57`  
		Last Modified: Thu, 11 May 2017 19:27:45 GMT  
		Size: 159.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec70fe50a2dd25761b7b4a81f82c388ba4476be52e73cf217d23bd9e9853bf8d`  
		Last Modified: Thu, 11 May 2017 21:27:00 GMT  
		Size: 2.1 KB (2068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:177aee627b5c161c0f62416c3a438b2edb391b96e3959ae62e78289150f299c5`  
		Last Modified: Thu, 11 May 2017 21:27:04 GMT  
		Size: 14.4 MB (14426550 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb123e2b5ed128671cd129961e7ce7221586a27bd4455dba0102abf98c8f8717`  
		Last Modified: Thu, 11 May 2017 21:27:01 GMT  
		Size: 818.8 KB (818811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d81a122790e3ed72a5d37e1a0a22fdd325667fc4cac22b60195e9b7a0a758dab`  
		Last Modified: Thu, 11 May 2017 21:26:58 GMT  
		Size: 7.3 KB (7291 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6901716757e38e7d064b904801e4b1e899f912ed28ab5f2762bf0442d85d8c9`  
		Last Modified: Thu, 11 May 2017 21:27:15 GMT  
		Size: 59.2 MB (59239865 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61d37924d8f63da2bda573f3add2b587ff933466ab175288fb4e01580ac63348`  
		Last Modified: Thu, 11 May 2017 21:26:58 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46d0a088b21967cc557a47b4fc3efa95d8ecd31dc4a92af34673d9e74d0826fe`  
		Last Modified: Thu, 11 May 2017 21:30:50 GMT  
		Size: 2.4 MB (2388321 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1fa73662c6897f079ad526cb70e68c01e68d5fc1a9dfc2c8875ad99a4a54189e`  
		Last Modified: Thu, 11 May 2017 21:30:59 GMT  
		Size: 76.4 MB (76448958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8039249e3c6885a5282c344be10ced8f0531f1376591d7424ebf16465c3aeded`  
		Last Modified: Thu, 11 May 2017 21:30:50 GMT  
		Size: 1.5 KB (1535 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b337e4d4ea327a1d3458236403accf5d69397839d6a8f5bcb8331b4ecf6cb4ee`  
		Last Modified: Mon, 15 May 2017 21:54:55 GMT  
		Size: 15.1 MB (15062862 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71f298964fc78388c750d6081d899b1855877ca399e7060852281a5f18112af7`  
		Last Modified: Mon, 15 May 2017 21:54:54 GMT  
		Size: 4.2 MB (4199892 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
