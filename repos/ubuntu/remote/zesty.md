## `ubuntu:zesty`

```console
$ docker pull ubuntu@sha256:e261b66433569bdec1ded5a1aba12dc8701ce75ece9551f545a39bd9612bba96
```

-	Platforms:
	-	linux; amd64

### `ubuntu:zesty` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **37.6 MB (37594894 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3855d928c7071d5fcfb80cb6d937484aa2d17be2521cd6f7972f8a1d3ccd3c0a`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Mon, 15 May 2017 16:45:15 GMT
ADD file:474024cdd432e6310b1600ec7a7ad514441b78931e54c88649d80210dc1b8dff in / 
# Mon, 15 May 2017 16:45:17 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Mon, 15 May 2017 16:45:18 GMT
RUN rm -rf /var/lib/apt/lists/*
# Mon, 15 May 2017 16:45:20 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Mon, 15 May 2017 16:45:21 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Mon, 15 May 2017 16:45:22 GMT
CMD ["/bin/bash"]
```

-	Layers:
	-	`sha256:0a7126bd8a6b99542baff88a3b3d6060f757015b9d0b9eefc67262a3105e8f5b`  
		Last Modified: Mon, 15 May 2017 16:52:05 GMT  
		Size: 37.6 MB (37592623 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae94a3e53d4ca5a11895528c17edf53bd66ba70a09e54ffe9a6e4b1d20aff1b7`  
		Last Modified: Mon, 15 May 2017 16:51:58 GMT  
		Size: 816.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aac23aaae9d8dfc439fa83d11efd459fbc2f13fede461588d7aef3a99c674415`  
		Last Modified: Mon, 15 May 2017 16:51:58 GMT  
		Size: 441.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f895d18390bae5533dc556f8c3f5a4a9d48ad8d8069568b508caed897d55825`  
		Last Modified: Mon, 15 May 2017 16:51:59 GMT  
		Size: 852.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37729941d4733d0d479a3fd2eb177e754711c7b4ac0f2a7a267a708f29e19a14`  
		Last Modified: Mon, 15 May 2017 16:51:59 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
