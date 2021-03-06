## `mongo:latest`

```console
$ docker pull mongo@sha256:2dd49be30907c901a3312f0452ba57128ca6449378cfe9d19ad01732a873d3bd
```

-	Platforms:
	-	linux; amd64

### `mongo:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **131.9 MB (131939233 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0bd4809a04a1ffbebf1e703657cc21f549fc9a43de12ae3182e369b6bd5c1804`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Mon, 08 May 2017 23:28:58 GMT
ADD file:7dc8fe041ca97fe00af650b41599e0b8d68188f7586ec0009b2cbe7d66896ba8 in / 
# Mon, 08 May 2017 23:28:59 GMT
CMD ["/bin/bash"]
# Tue, 09 May 2017 17:32:07 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Tue, 09 May 2017 17:32:19 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 09 May 2017 17:32:20 GMT
ENV GOSU_VERSION=1.7
# Tue, 09 May 2017 17:32:37 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove wget
# Tue, 09 May 2017 17:32:38 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 09 May 2017 17:32:39 GMT
ENV GPG_KEYS=0C49F3730359A14518585931BC711F9BA15703C6
# Tue, 09 May 2017 17:32:42 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 09 May 2017 17:32:42 GMT
ENV MONGO_MAJOR=3.4
# Tue, 09 May 2017 17:32:43 GMT
ENV MONGO_VERSION=3.4.4
# Tue, 09 May 2017 17:32:44 GMT
ENV MONGO_PACKAGE=mongodb-org
# Tue, 09 May 2017 17:32:45 GMT
RUN echo "deb http://repo.mongodb.org/apt/debian jessie/mongodb-org/$MONGO_MAJOR main" > /etc/apt/sources.list.d/mongodb-org.list
# Tue, 09 May 2017 17:33:02 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Tue, 09 May 2017 17:33:04 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Tue, 09 May 2017 17:33:05 GMT
VOLUME [/data/db /data/configdb]
# Tue, 09 May 2017 17:33:06 GMT
COPY file:7c445c3da5fdc0495368be2c40f1d2a4cd7590cf458336174c54b078324bb71f in /usr/local/bin/ 
# Tue, 09 May 2017 17:33:08 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Tue, 09 May 2017 17:33:09 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Tue, 09 May 2017 17:33:09 GMT
EXPOSE 27017/tcp
# Tue, 09 May 2017 17:33:10 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:56c7afbcb0f1f3976c78e9c511ded74db33dfc196fe4b4b56914d7b1917c5aa2`  
		Last Modified: Mon, 08 May 2017 23:45:51 GMT  
		Size: 30.6 MB (30636650 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ac4863389b54fa744b9eb1c6836ddb0a70ccb814eccb8e75ae45785668d65c27`  
		Last Modified: Sat, 13 May 2017 07:09:59 GMT  
		Size: 2.1 KB (2065 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fccbd1684456166859eed5a3a3f6e1edc4732fb88cbe51aaad69617e1075187d`  
		Last Modified: Sat, 13 May 2017 07:11:05 GMT  
		Size: 2.4 MB (2404284 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5565b5f177e7fbb9611b5212b67311421f12988629093757be24c6c2b69084c2`  
		Last Modified: Sat, 13 May 2017 07:11:04 GMT  
		Size: 888.6 KB (888621 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b00971241c470ff0e96d281740cba4662deaf5c5284df2e3dc45652f9297d685`  
		Last Modified: Sat, 13 May 2017 07:11:04 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c0300dc073745cbbb411a99ed6855de8fcf855dbc2ca648badeaec3b4eb5fe4f`  
		Last Modified: Sat, 13 May 2017 07:11:01 GMT  
		Size: 1.4 KB (1434 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b93b8ba2b93b970864e68917ce3369bbdd02717bed3e3c3b6b1d4cbd87948904`  
		Last Modified: Sat, 13 May 2017 07:11:01 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:661362338965ff4fd49b58a49dd1fd24bb25d4bc65d8e3fd702ab296ac9d7852`  
		Last Modified: Sat, 13 May 2017 07:11:22 GMT  
		Size: 98.0 MB (98002670 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa170e22de2e3c20397635daf87fd2c8ad319f6756004822ff28004cb16f4522`  
		Last Modified: Sat, 13 May 2017 07:11:01 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22670c2d1be4c9a6a02782ab32bb334c4751e74899807009c6ebcf9f4883a95d`  
		Last Modified: Sat, 13 May 2017 07:11:01 GMT  
		Size: 2.9 KB (2911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2efb0cd1fb79dd818ec211043ee866c6def0756fb2be68f27c32d1a624557ac2`  
		Last Modified: Sat, 13 May 2017 07:11:01 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
