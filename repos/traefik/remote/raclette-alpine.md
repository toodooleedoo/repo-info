## `traefik:raclette-alpine`

```console
$ docker pull traefik@sha256:5013be9b43e67072e3916975f4aef6339d4148d6f8d9f109ebf6dc036fbfdec6
```

-	Platforms:
	-	linux; amd64

### `traefik:raclette-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **15.5 MB (15541098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c70ebd7864d031e3da9653424ace40c8f311403b34bcb5a628051798c0d4277a`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["--help"]`

```dockerfile
# Wed, 10 May 2017 16:37:36 GMT
ADD file:9c596c6cb8ba1d7f93d4dc5fc3f42bfcd5edca57d5be5d60ea04ef42f55fb7a8 in / 
# Wed, 10 May 2017 16:37:37 GMT
CMD ["/bin/sh"]
# Wed, 10 May 2017 23:38:38 GMT
RUN apk --update upgrade     && apk --no-cache --no-progress add ca-certificates     && rm -rf /var/cache/apk/*
# Tue, 16 May 2017 17:25:02 GMT
COPY file:677dea3d35653f499e3230d8eb921ca0281fe450b5930a8b940fe5331c83c1c7 in /usr/local/bin/ 
# Tue, 16 May 2017 17:25:03 GMT
COPY file:41f5bd1ea0a61e819b7d8c5489c305d4f2798046917dd6b6695318f555981727 in / 
# Tue, 16 May 2017 17:25:04 GMT
EXPOSE 80/tcp
# Tue, 16 May 2017 17:25:05 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Tue, 16 May 2017 17:25:06 GMT
CMD ["--help"]
# Tue, 16 May 2017 17:25:07 GMT
LABEL org.label-schema.vendor=Containous org.label-schema.url=https://traefik.io org.label-schema.name=Traefik org.label-schema.description=A modern reverse-proxy org.label-schema.version=v1.3.0-rc2 org.label-schema.docker.schema-version=1.0
```

-	Layers:
	-	`sha256:79650cf9cc01ddb17cb9c4036ba9268528b775fe0322f347d15b5e4176928f34`  
		Last Modified: Wed, 10 May 2017 16:40:36 GMT  
		Size: 2.4 MB (2383037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce9026ef6e053e15387887a39afe45b491998cf4bd1281fc1a2779c399b82e7f`  
		Last Modified: Sat, 13 May 2017 19:36:47 GMT  
		Size: 346.8 KB (346820 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32ee7bbd2b93532249e3b451a321392f093d8f23148f3560b34cbdb40d80e624`  
		Last Modified: Tue, 16 May 2017 17:27:50 GMT  
		Size: 12.8 MB (12810901 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bfd841dcd9423db5faa9aeccb3a14272c1042d7fa36d9b3738fc4df9ad53b01`  
		Last Modified: Tue, 16 May 2017 17:27:48 GMT  
		Size: 340.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
