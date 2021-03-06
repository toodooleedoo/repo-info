## `odoo:latest`

```console
$ docker pull odoo@sha256:4142e69138d0f7ff28b63d3c0ae61921ab54a4160fa23a11f163756bde275a58
```

-	Platforms:
	-	linux; amd64

### `odoo:latest` - linux; amd64

-	Docker Version: 17.04.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **273.1 MB (273148206 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3c69d49c6245cb7c7b55c547f543e9b1e602efe5d41dd30d77be9e212790d12f`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["odoo"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Wed, 10 May 2017 13:47:47 GMT
MAINTAINER Odoo S.A. <info@odoo.com>
# Wed, 10 May 2017 13:48:29 GMT
RUN set -x;         apt-get update         && apt-get install -y --no-install-recommends             ca-certificates             curl             node-less             python-gevent             python-pip             python-renderpm             python-support             python-watchdog         && curl -o wkhtmltox.deb -SL http://nightly.odoo.com/extra/wkhtmltox-0.12.1.2_linux-jessie-amd64.deb         && echo '40e8b906de658a2221b15e4e8cd82565a47d7ee8 wkhtmltox.deb' | sha1sum -c -         && dpkg --force-depends -i wkhtmltox.deb         && apt-get -y install -f --no-install-recommends         && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false -o APT::AutoRemove::SuggestsImportant=false npm         && rm -rf /var/lib/apt/lists/* wkhtmltox.deb         && pip install psycogreen==1.0
# Wed, 10 May 2017 13:48:30 GMT
ENV ODOO_VERSION=10.0
# Wed, 10 May 2017 13:48:30 GMT
ENV ODOO_RELEASE=20170207
# Wed, 10 May 2017 13:49:32 GMT
RUN set -x;         curl -o odoo.deb -SL http://nightly.odoo.com/${ODOO_VERSION}/nightly/deb/odoo_${ODOO_VERSION}.${ODOO_RELEASE}_all.deb         && echo '5d2fb0cc03fa0795a7b2186bb341caa74d372e82 odoo.deb' | sha1sum -c -         && dpkg --force-depends -i odoo.deb         && apt-get update         && apt-get -y install -f --no-install-recommends         && rm -rf /var/lib/apt/lists/* odoo.deb
# Wed, 10 May 2017 13:49:34 GMT
COPY file:33fddeba88e5214ff2c7cd05a02348dc417a5de70b767d6ff559e871ee6d046a in / 
# Wed, 10 May 2017 13:49:35 GMT
COPY file:18e3dbead2bc096fe44ef1cfaa2a6e8dc1b27daeeb1d281cfdd552b805f2e767 in /etc/odoo/ 
# Wed, 10 May 2017 13:49:36 GMT
RUN chown odoo /etc/odoo/odoo.conf
# Wed, 10 May 2017 13:49:38 GMT
RUN mkdir -p /mnt/extra-addons         && chown -R odoo /mnt/extra-addons
# Wed, 10 May 2017 13:49:39 GMT
VOLUME [/var/lib/odoo /mnt/extra-addons]
# Wed, 10 May 2017 13:49:40 GMT
EXPOSE 8069/tcp 8071/tcp
# Wed, 10 May 2017 13:49:40 GMT
ENV ODOO_RC=/etc/odoo/odoo.conf
# Wed, 10 May 2017 13:49:41 GMT
USER [odoo]
# Wed, 10 May 2017 13:49:42 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 10 May 2017 13:49:43 GMT
CMD ["odoo"]
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80aa58b4cb7976b895be10950a1a981bff8b7ba15440169e342e06a0600a48c3`  
		Last Modified: Sat, 13 May 2017 09:01:31 GMT  
		Size: 88.7 MB (88741792 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78a34f15fdb3d7e10dab4b69e156cb7be11c3a43f47a8c1b2f5de0d95b407d82`  
		Last Modified: Sat, 13 May 2017 09:01:59 GMT  
		Size: 131.8 MB (131820515 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:265338d935fd43338ef074726e9995fd2c91d7e5ca082131e1d202cd88d460b8`  
		Last Modified: Sat, 13 May 2017 09:01:11 GMT  
		Size: 599.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:db91a24bbd5da5cf5a0eae8b64826206c5e0f3b80080840260988a8f646d794e`  
		Last Modified: Sat, 13 May 2017 09:01:11 GMT  
		Size: 578.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:048f4c8f00995ab3581fee64f1c6368691fa616a6550ccdc45fc7b108c12b57f`  
		Last Modified: Sat, 13 May 2017 09:01:11 GMT  
		Size: 581.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40cd128d4abe1574532dffbb0917474c829665714d6f7ee3e3c84f8a5142813e`  
		Last Modified: Sat, 13 May 2017 09:01:11 GMT  
		Size: 125.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
