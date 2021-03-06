## `redis:32bit`

```console
$ docker pull redis@sha256:c34ce7080020ed50dcf174bcc6e81b6fdc1e8930a9cfd917cab29f87824855ef
```

-	Platforms:
	-	linux; amd64

### `redis:32bit` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **80.1 MB (80101844 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:84a07f084ab65e30aa77e37cd15b5b4b0273dc213f6df4d9ee3f8ebf4d0969e4`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Wed, 10 May 2017 15:42:16 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 10 May 2017 15:42:31 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 15:42:32 GMT
ENV GOSU_VERSION=1.7
# Wed, 10 May 2017 15:42:37 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Thu, 18 May 2017 22:25:01 GMT
ENV REDIS_VERSION=3.2.9
# Thu, 18 May 2017 22:25:02 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-3.2.9.tar.gz
# Thu, 18 May 2017 22:25:03 GMT
ENV REDIS_DOWNLOAD_SHA=6eaacfa983b287e440d0839ead20c2231749d5d6b78bbe0e0ffa3a890c59ff26
# Thu, 18 May 2017 22:26:29 GMT
RUN apt-get update && apt-get install -y libc6-i386 --no-install-recommends && rm -rf /var/lib/apt/lists/*
# Thu, 18 May 2017 22:27:23 GMT
RUN set -ex 		&& buildDeps=' 		gcc 		gcc-multilib 		libc6-dev-i386 		make 	' 	&& apt-get update 	&& apt-get install -y $buildDeps --no-install-recommends 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL" 	&& echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c - 	&& mkdir -p /usr/src/redis 	&& tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1 	&& rm redis.tar.gz 		&& grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h 	&& sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h 	&& grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h 		&& make -C /usr/src/redis 32bit 	&& make -C /usr/src/redis install 		&& rm -r /usr/src/redis 		&& apt-get purge -y --auto-remove $buildDeps
# Thu, 18 May 2017 22:27:25 GMT
RUN mkdir /data && chown redis:redis /data
# Thu, 18 May 2017 22:27:25 GMT
VOLUME [/data]
# Thu, 18 May 2017 22:27:26 GMT
WORKDIR /data
# Thu, 18 May 2017 22:27:28 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Thu, 18 May 2017 22:27:28 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 18 May 2017 22:27:29 GMT
EXPOSE 6379/tcp
# Thu, 18 May 2017 22:27:30 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b690bc4eaa6434456ceaccf9b3e42229bd2691869ba439e515b28fe1a66c009`  
		Last Modified: Sat, 13 May 2017 18:16:18 GMT  
		Size: 2.1 KB (2062 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4cdd94354d2a873333a205a02dbb853dd763c73600e0cf64f60b4bd7ab694875`  
		Last Modified: Sat, 13 May 2017 18:16:20 GMT  
		Size: 17.3 MB (17300175 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71c1f30d820f0457df186531dc4478967d075ba449bd3168a3e82137a47daf03`  
		Last Modified: Sat, 13 May 2017 18:16:16 GMT  
		Size: 818.8 KB (818811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:59a565e615f8d163739c9dd88f339a29488c3b3606335ce356758007687983fb`  
		Last Modified: Thu, 18 May 2017 22:33:17 GMT  
		Size: 4.4 MB (4360725 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c55b5c6fb04ff1959cc2e01c38b252547142e16ba43c5255f3ca4e7bab6a293e`  
		Last Modified: Thu, 18 May 2017 22:33:17 GMT  
		Size: 5.0 MB (5035562 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9cddc681e1e857c60911e10e2224ce9a09b85913095e1fbfe5ab7ac75018b5a`  
		Last Modified: Thu, 18 May 2017 22:33:16 GMT  
		Size: 97.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70a839c9140bf212bfe4503bf969f352e983bed590e1e27cd1157edc75ef1109`  
		Last Modified: Thu, 18 May 2017 22:33:16 GMT  
		Size: 396.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
