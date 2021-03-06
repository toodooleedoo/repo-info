## `pypy:2-slim`

```console
$ docker pull pypy@sha256:9930528595de61fccc73b0d16bbc108e10a944636c9a92ac433452d5983e1b9a
```

-	Platforms:
	-	linux; amd64

### `pypy:2-slim` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **84.8 MB (84800519 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4d546f64059ba06d2f8348d786a45e07423611f702453825dcd1b43ce947a71f`
-	Default Command: `["pypy"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Wed, 10 May 2017 02:59:09 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 10 May 2017 02:59:27 GMT
ENV LANG=C.UTF-8
# Wed, 10 May 2017 15:27:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libexpat1 		libffi6 		libgdbm3 		libsqlite3-0 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 15:27:25 GMT
ENV PYPY_VERSION=5.7.1
# Wed, 10 May 2017 15:27:25 GMT
ENV PYPY_SHA256SUM=c4fa3da42156bed4a9d912433b618a141e0c5161d7cc8c328786736ea5d1c2da
# Wed, 10 May 2017 15:27:26 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Wed, 10 May 2017 15:27:55 GMT
RUN set -ex 	&& fetchDeps=' 		bzip2 		wget 	' 	&& apt-get update && apt-get install -y $fetchDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& wget -O pypy.tar.bz2 "https://bitbucket.org/pypy/pypy/downloads/pypy2-v${PYPY_VERSION}-linux64.tar.bz2" 	&& echo "$PYPY_SHA256SUM  pypy.tar.bz2" | sha256sum -c 	&& tar -xjC /usr/local --strip-components=1 -f pypy.tar.bz2 	&& rm pypy.tar.bz2 			&& wget -O /tmp/get-pip.py 'https://bootstrap.pypa.io/get-pip.py' 		&& pypy /tmp/get-pip.py "pip==$PYTHON_PIP_VERSION" 		&& rm /tmp/get-pip.py 	&& pip install --no-cache-dir --upgrade --force-reinstall "pip==$PYTHON_PIP_VERSION" 	&& [ "$(pip list |tac|tac| awk -F '[ ()]+' '$1 == "pip" { print $2; exit }')" = "$PYTHON_PIP_VERSION" ] 		&& apt-get purge -y --auto-remove $fetchDeps 	&& rm -rf ~/.cache
# Wed, 10 May 2017 15:27:55 GMT
CMD ["pypy"]
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3110ef7d6181163f7662045163b6f95a90f2879c3e8b3c14c77748bd52d6dacd`  
		Last Modified: Sat, 13 May 2017 17:58:14 GMT  
		Size: 3.6 MB (3639986 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5663802950c48a67d9f4e9194a7ab87141cb603a29637bbf05c0aac67616c5aa`  
		Last Modified: Sat, 13 May 2017 17:58:22 GMT  
		Size: 28.6 MB (28576517 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
