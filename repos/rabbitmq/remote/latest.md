## `rabbitmq:latest`

```console
$ docker pull rabbitmq@sha256:727c1f4df2df1c31ce1172e0589ef0a680d2d4c295cc3b4bfef9a97ef1ca2676
```

-	Platforms:
	-	linux; amd64

### `rabbitmq:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **87.9 MB (87945458 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:951e8c07aaa5e49f5012af309713b9a1329a149d988761a97c646233b786bbdb`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["rabbitmq-server"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Wed, 10 May 2017 15:31:23 GMT
RUN groupadd -r rabbitmq && useradd -r -d /var/lib/rabbitmq -m -g rabbitmq rabbitmq
# Wed, 10 May 2017 15:31:24 GMT
ENV GOSU_VERSION=1.7
# Wed, 10 May 2017 15:31:43 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Wed, 10 May 2017 15:31:46 GMT
RUN set -ex; 	key='434975BD900CCBE4F7EE1B1ED208507CA14F4FCA'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/erlang-solutions.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 10 May 2017 15:31:48 GMT
RUN echo 'deb http://packages.erlang-solutions.com/debian jessie contrib' > /etc/apt/sources.list.d/erlang.list
# Wed, 10 May 2017 15:32:19 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		erlang-asn1 		erlang-base-hipe 		erlang-crypto 		erlang-eldap 		erlang-inets 		erlang-mnesia 		erlang-nox 		erlang-os-mon 		erlang-public-key 		erlang-ssl 		erlang-xmerl 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 15:32:20 GMT
ENV RABBITMQ_LOGS=- RABBITMQ_SASL_LOGS=-
# Wed, 10 May 2017 15:32:23 GMT
RUN set -ex; 	key='0A9AF2115F4687BD29803A206B73A36E6026DFCA'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/rabbitmq.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 10 May 2017 15:32:24 GMT
RUN echo 'deb http://www.rabbitmq.com/debian testing main' > /etc/apt/sources.list.d/rabbitmq.list
# Wed, 10 May 2017 15:32:25 GMT
ENV RABBITMQ_VERSION=3.6.9
# Wed, 10 May 2017 15:32:26 GMT
ENV RABBITMQ_DEBIAN_VERSION=3.6.9-1
# Wed, 10 May 2017 15:32:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		rabbitmq-server=$RABBITMQ_DEBIAN_VERSION 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 15:32:37 GMT
ENV PATH=/usr/lib/rabbitmq/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 10 May 2017 15:32:37 GMT
ENV HOME=/var/lib/rabbitmq
# Wed, 10 May 2017 15:32:39 GMT
RUN mkdir -p /var/lib/rabbitmq /etc/rabbitmq 	&& chown -R rabbitmq:rabbitmq /var/lib/rabbitmq /etc/rabbitmq 	&& chmod -R 777 /var/lib/rabbitmq /etc/rabbitmq
# Wed, 10 May 2017 15:32:40 GMT
VOLUME [/var/lib/rabbitmq]
# Wed, 10 May 2017 15:32:42 GMT
RUN ln -sf /var/lib/rabbitmq/.erlang.cookie /root/
# Wed, 10 May 2017 15:32:44 GMT
RUN ln -sf /usr/lib/rabbitmq/lib/rabbitmq_server-$RABBITMQ_VERSION/plugins /plugins
# Wed, 10 May 2017 15:32:45 GMT
COPY file:e75247400159c3b996450d9b4ef7078cf9587833f465ab2904b2b7ef35be65e9 in /usr/local/bin/ 
# Wed, 10 May 2017 15:32:47 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 10 May 2017 15:32:47 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 10 May 2017 15:32:48 GMT
EXPOSE 25672/tcp 4369/tcp 5671/tcp 5672/tcp
# Wed, 10 May 2017 15:32:49 GMT
CMD ["rabbitmq-server"]
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ad3529559716ef2226d04b49688e86c4e33e25788838dce402a97e3b9cb4357`  
		Last Modified: Sat, 13 May 2017 18:07:30 GMT  
		Size: 4.4 KB (4376 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8d6f7fd21c4b2507908ced40197cca24acbeaf097f52fa31a0f88b63830d7f4`  
		Last Modified: Sat, 13 May 2017 18:07:30 GMT  
		Size: 1.3 MB (1307776 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4971849d324fe6ca2ba0aef4418bb06d9999a0bf90527f86ba6e916ff0bbd2bc`  
		Last Modified: Sat, 13 May 2017 18:07:28 GMT  
		Size: 2.5 KB (2502 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c4afa2fcab88b38bb66b17fb0162c5a7d5175984afd079022afdc6a65f18acd`  
		Last Modified: Sat, 13 May 2017 18:07:28 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a846993595cb3919b6d37f55dc1e1ac7f593a8ff7dd58d3f2d03dc64e8a2d43`  
		Last Modified: Sat, 13 May 2017 18:07:32 GMT  
		Size: 28.3 MB (28347945 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:afe1747cbdec723d9f40051e657d28358e6a09f751ccb1a2ea807a44f27d5e8d`  
		Last Modified: Sat, 13 May 2017 18:07:27 GMT  
		Size: 3.1 KB (3099 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4773d4648f681e6de65dddf61ca22be624193850b6d76a93ee78f0305926dca`  
		Last Modified: Sat, 13 May 2017 18:07:27 GMT  
		Size: 213.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:688ad704b3d6c315c85950ea57b88828b503dfbda346cfec7a67ff5696be5443`  
		Last Modified: Sat, 13 May 2017 18:07:27 GMT  
		Size: 5.7 MB (5688635 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9231ad18e7e05cc9a23d5dee0da6fec4c244dbc7a51fdf3a62fe3684484b4c5`  
		Last Modified: Sat, 13 May 2017 18:07:25 GMT  
		Size: 2.2 KB (2235 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5d61ea7157c3846a88fd941c91944d00d952024cdf752292b6f781a2facd7896`  
		Last Modified: Sat, 13 May 2017 18:07:25 GMT  
		Size: 146.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8434d606daac7763521c20374d53137462c6c49c5af7a9e0da9bf7a060a8cd59`  
		Last Modified: Sat, 13 May 2017 18:07:26 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f4f553d4a4f79651cb301196df2e5ed4cdcd5e9fcbd91696cff44f7ce2e2bdc`  
		Last Modified: Sat, 13 May 2017 18:07:25 GMT  
		Size: 4.0 KB (4043 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33d7e2eca442f194f7d6d157df36e37a0eb8ed850bb79c21427fe21928c440e0`  
		Last Modified: Sat, 13 May 2017 18:07:25 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
