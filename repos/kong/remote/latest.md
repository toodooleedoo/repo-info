## `kong:latest`

```console
$ docker pull kong@sha256:ff6dd0495f1a5b312bff9fd42f6aee6437200a337e190eb0ddc8e5ca83482995
```

-	Platforms:
	-	linux; amd64

### `kong:latest` - linux; amd64

-	Docker Version: 1.12.1
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **122.4 MB (122370149 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e24e4a80083e78712c63dd04e1cb5543f867e05290b43cc1a8e827ac05af3159`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["kong","start"]`

```dockerfile
# Thu, 11 May 2017 19:45:46 GMT
ADD file:f3be3f14a2136b0c38b2d80b90cb1f3bbe5b3c78d35a94f3a0f1fe4219e1806f in / 
# Thu, 11 May 2017 19:45:48 GMT
LABEL name=CentOS Base Image vendor=CentOS license=GPLv2 build-date=20170510
# Thu, 11 May 2017 19:45:49 GMT
CMD ["/bin/bash"]
# Thu, 11 May 2017 19:58:34 GMT
MAINTAINER Marco Palladino, marco@mashape.com
# Thu, 11 May 2017 19:58:35 GMT
ENV KONG_VERSION=0.10.2
# Thu, 11 May 2017 19:59:06 GMT
RUN yum install -y wget https://github.com/Mashape/kong/releases/download/$KONG_VERSION/kong-$KONG_VERSION.el7.noarch.rpm &&     yum clean all
# Thu, 11 May 2017 19:59:08 GMT
RUN wget -O /usr/local/bin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.1.3/dumb-init_1.1.3_amd64 &&     chmod +x /usr/local/bin/dumb-init
# Thu, 11 May 2017 19:59:09 GMT
COPY file:e806c057c1c71a8dd5e684244eed51d4ff17ca43efe7233573320a3bf8dda3a4 in /docker-entrypoint.sh 
# Thu, 11 May 2017 19:59:10 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 11 May 2017 19:59:11 GMT
EXPOSE 7946/tcp 8000/tcp 8001/tcp 8443/tcp
# Thu, 11 May 2017 19:59:12 GMT
CMD ["kong" "start"]
```

-	Layers:
	-	`sha256:343b0936103607602d236363460c0368a1cad0ef58a534d5a5c2ecd9f8c2f3dd`  
		Last Modified: Thu, 11 May 2017 19:46:47 GMT  
		Size: 70.5 MB (70522725 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb953d76e90b35f738d5b2ce1e92ace363c0d21c17bc3e384de5e264458d5815`  
		Last Modified: Thu, 11 May 2017 20:00:07 GMT  
		Size: 51.8 MB (51822555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ebdf6ecbe50964a86be21ba78e3fd6f5cf86fccd3d518da0b36f2498a06c3a37`  
		Last Modified: Thu, 11 May 2017 19:59:49 GMT  
		Size: 24.6 KB (24648 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:24f20231ced9616fe8ffb824d208a2da93cbfae7cc5add4f60f93d7f5f34aaa8`  
		Last Modified: Thu, 11 May 2017 19:59:50 GMT  
		Size: 221.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
