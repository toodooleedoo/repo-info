## `fsharp:latest`

```console
$ docker pull fsharp@sha256:eeb896045083a04c62ecc22a74991337a61c4e1b421f97c03d3ad4347762b323
```

-	Platforms:
	-	linux; amd64

### `fsharp:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **340.4 MB (340448725 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:19891a1f0808a1e275caaffe5f26781ae3500eb3ee5f7971444c7cb99084123d`
-	Default Command: `["fsharpi"]`

```dockerfile
# Mon, 15 May 2017 16:42:44 GMT
ADD file:352ee0cc1cc352d862c55cade419e2e7b64a63c663b896d8014efdf44008bce4 in / 
# Mon, 15 May 2017 16:42:46 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Mon, 15 May 2017 16:42:47 GMT
RUN rm -rf /var/lib/apt/lists/*
# Mon, 15 May 2017 16:42:49 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Mon, 15 May 2017 16:42:50 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Mon, 15 May 2017 16:42:51 GMT
CMD ["/bin/bash"]
# Mon, 15 May 2017 17:05:03 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Mon, 15 May 2017 17:05:46 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Mon, 15 May 2017 17:07:22 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Mon, 15 May 2017 20:10:58 GMT
LABEL maintainer=Dave Curylo <dave@curylo.org>, Steve Desmond <steve@stevedesmond.ca>
# Mon, 15 May 2017 20:50:34 GMT
ENV MONO_VERSION=4.8.1.0
# Mon, 15 May 2017 20:50:38 GMT
RUN apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF &&     echo "deb http://download.mono-project.com/repo/debian wheezy/snapshots/$MONO_VERSION main" > /etc/apt/sources.list.d/mono-xamarin.list
# Mon, 15 May 2017 20:50:57 GMT
ENV MONO_THREADS_PER_CPU=50
# Mon, 15 May 2017 20:51:50 GMT
RUN apt-get -y update &&     apt-get -y --no-install-recommends install nuget mono-devel ca-certificates-mono &&     rm -rf /var/lib/apt/lists/*
# Mon, 15 May 2017 20:52:08 GMT
ENV FSHARP_VERSION=4.1.18
# Mon, 15 May 2017 20:52:09 GMT
ENV FSHARP_PREFIX=/usr FSHARP_GACDIR=/usr/lib/mono/gac FSHARP_BASENAME=fsharp-4.1.18 FSHARP_ARCHIVE=4.1.18.tar.gz FSHARP_ARCHIVE_URL=https://github.com/fsharp/fsharp/archive/4.1.18.tar.gz
# Mon, 15 May 2017 21:00:17 GMT
RUN mkdir -p /tmp/src &&     cd /tmp/src &&     wget $FSHARP_ARCHIVE_URL &&     tar xf $FSHARP_ARCHIVE &&     cd $FSHARP_BASENAME &&     ./autogen.sh --prefix=$FSHARP_PREFIX --with-gacdir=$FSHARP_GACDIR &&     make &&     make install &&     cd ~ &&     rm -rf /tmp/src
# Mon, 15 May 2017 21:00:35 GMT
WORKDIR /root
# Mon, 15 May 2017 21:00:36 GMT
CMD ["fsharpi"]
```

-	Layers:
	-	`sha256:cf0a75889057c9255505ce5ef36a0d00ac480c945557adfb12674417a0d3efed`  
		Last Modified: Mon, 15 May 2017 16:47:33 GMT  
		Size: 67.1 MB (67103479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8de9902faf0bd04893447386c8aeeb1e551b3b6622470f4eb838428359672d7`  
		Last Modified: Mon, 15 May 2017 16:47:22 GMT  
		Size: 72.6 KB (72621 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3c0f7711c5e6b6f9181958c18daa56809bfa45a03f3a45da4cd0d83675dd896`  
		Last Modified: Mon, 15 May 2017 16:47:22 GMT  
		Size: 364.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6391432e12cf7305a906d4264230c98cfe04f9a96ba2d97305964ad1b709986`  
		Last Modified: Mon, 15 May 2017 16:47:22 GMT  
		Size: 675.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:624ce029a17f47b8a009a436b1190e11820261f63408a1e7e213d30845c1d0ab`  
		Last Modified: Mon, 15 May 2017 16:47:22 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4b91e692e7824d309e2aacbfb74b09f492a90064fd976acb7ade04823a585fb`  
		Last Modified: Mon, 15 May 2017 17:51:27 GMT  
		Size: 4.7 MB (4705649 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5e31ac06c5da4207bc350f5e780dcc68e7224abed4e5feec0ba8edb12cb5dbe2`  
		Last Modified: Mon, 15 May 2017 17:52:14 GMT  
		Size: 29.5 MB (29544928 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:081b51ed23b603deb7be697d375a35c78a586d9411b1d23311b80b797ed3824c`  
		Last Modified: Mon, 15 May 2017 17:53:12 GMT  
		Size: 105.4 MB (105362899 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1386f36787b8593c2943cb5fb6d9bbb71e1740920bc66aa40301909313defd6d`  
		Last Modified: Mon, 15 May 2017 21:05:00 GMT  
		Size: 13.8 KB (13816 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78b23e774f9cb3f0104810110f1c4f92fc44695c59ac15d5088aa6919429c9a3`  
		Last Modified: Mon, 15 May 2017 21:05:13 GMT  
		Size: 55.0 MB (54951609 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b38de91a9bb53652bb287d6a4eb95fe5e4897633b37826dd384f6b0d0373603`  
		Last Modified: Mon, 15 May 2017 21:05:14 GMT  
		Size: 78.7 MB (78692523 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
