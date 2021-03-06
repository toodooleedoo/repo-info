## `ubuntu:devel`

```console
$ docker pull ubuntu@sha256:0fda3973dca01bb6797c8f84f7728730e3760fff0360b213bb1a8f2a65492967
```

-	Platforms:
	-	linux; amd64

### `ubuntu:devel` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **37.1 MB (37111788 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:073e7b409b9b1b8691820453bba3315ecb5a47fb52270f85c4e9d1418ad2c3eb`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 15 May 2017 16:41:51 GMT
ADD file:55b9126900211a70f30d8684ab28d2c5abb9ab42436bc7335c6bd9d2b8f9a0b1 in / 
# Mon, 15 May 2017 16:41:52 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Mon, 15 May 2017 16:41:54 GMT
RUN rm -rf /var/lib/apt/lists/*
# Mon, 15 May 2017 16:41:55 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Mon, 15 May 2017 16:41:57 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Mon, 15 May 2017 16:41:57 GMT
CMD ["/bin/bash"]
```

-	Layers:
	-	`sha256:06d6d7dd14f081e36ce2140e75da9d2be41ec3c184473526851222d43317340a`  
		Last Modified: Mon, 15 May 2017 16:45:51 GMT  
		Size: 37.1 MB (37109572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7afd309907db7dbf986cfa50ebf787c214836179341cf115a38d60d967d59476`  
		Last Modified: Mon, 15 May 2017 16:45:46 GMT  
		Size: 816.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:151009f8900b8d5894eb0ee02bb46edbdc6542f0e992377a9b9ae2fc28ced7a7`  
		Last Modified: Mon, 15 May 2017 16:45:46 GMT  
		Size: 387.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36547d3d8f4e6250dba0bdce6fe7ba5aa302ad03fe7e363dc7286dfe3a35d8be`  
		Last Modified: Mon, 15 May 2017 16:45:47 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:320476e1abe24cdee7fe0da59afd08414429e49896040ebd7dd0987db6a030ac`  
		Last Modified: Mon, 15 May 2017 16:45:46 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
