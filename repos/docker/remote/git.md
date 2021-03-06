## `docker:git`

```console
$ docker pull docker@sha256:cff7bb2491ef93d847db86f2cf8e2fef6bd00a9c9ee8a07747f2af939ef74cc6
```

-	Platforms:
	-	linux; amd64

### `docker:git` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.1 MB (42062852 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ce25da2236f03c3d2fdf48e4ffecba425ac937e906cbaf4e469614725989a3c`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Wed, 10 May 2017 16:38:16 GMT
ADD file:63f63606d6e289eb607c90e31de81802258906712727e473a2898f0f1ae55bb5 in / 
# Wed, 10 May 2017 16:38:17 GMT
CMD ["/bin/sh"]
# Fri, 19 May 2017 19:24:36 GMT
RUN apk add --no-cache 		ca-certificates
# Fri, 19 May 2017 19:24:37 GMT
ENV DOCKER_CHANNEL=edge
# Fri, 19 May 2017 19:24:38 GMT
ENV DOCKER_VERSION=17.05.0-ce
# Fri, 19 May 2017 19:24:45 GMT
RUN set -ex; 	apk add --no-cache --virtual .fetch-deps 		curl 		tar 	; 	curl -fL -o docker.tgz "https://download.docker.com/linux/static/${DOCKER_CHANNEL}/x86_64/docker-${DOCKER_VERSION}.tgz"; 	tar --extract 		--file docker.tgz 		--strip-components 1 		--directory /usr/local/bin/ 	; 	rm docker.tgz; 	apk del .fetch-deps; 	dockerd -v; 	docker -v
# Fri, 19 May 2017 19:24:46 GMT
COPY file:a8b1446f032ff01ac092c29a0af328f0b9d47bbee72d1049499f2a9a89ee988a in /usr/local/bin/ 
# Fri, 19 May 2017 19:24:47 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 19 May 2017 19:24:48 GMT
CMD ["sh"]
# Fri, 19 May 2017 19:25:50 GMT
RUN apk add --no-cache 		git 		openssh-client
```

-	Layers:
	-	`sha256:cfc728c1c5584d8e0ae69368fc9c34d54d72651355573ba42554c2469a0a6299`  
		Last Modified: Wed, 10 May 2017 16:41:01 GMT  
		Size: 2.0 MB (1967906 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b405897e6fd8e625849a4b5a7f1ab0577b167f7acc204ac1fa0ba4a3e118133b`  
		Last Modified: Fri, 19 May 2017 19:27:49 GMT  
		Size: 350.6 KB (350634 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7463945bc18207b456de53fa78695ebc4993bc3d24088b30c7553074080cc6eb`  
		Last Modified: Fri, 19 May 2017 19:27:56 GMT  
		Size: 28.8 MB (28753619 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:305297ec566a1e97bd753326b03d3e1795ff0067c7fd1355f9a9502817a015df`  
		Last Modified: Fri, 19 May 2017 19:27:49 GMT  
		Size: 489.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fe8107f9f4b97908a42d562b84df3f21ca6662c18eec594800d062dbbdb305d`  
		Last Modified: Fri, 19 May 2017 19:32:39 GMT  
		Size: 11.0 MB (10990204 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
