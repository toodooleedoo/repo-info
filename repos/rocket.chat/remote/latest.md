## `rocket.chat:latest`

```console
$ docker pull rocket.chat@sha256:a7b7e5bbca73e0c7fefaca44fb3746ada59e2904d8fc873d4e292fdc4b5eb9c1
```

-	Platforms:
	-	linux; amd64

### `rocket.chat:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **201.3 MB (201321780 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc68d0970353b749036684fafcc4d0839c513da7c98f06ea1c13424a9f413129`
-	Default Command: `["node","main.js"]`

```dockerfile
# Mon, 08 May 2017 23:28:14 GMT
ADD file:f4e6551ac34ab446a297849489a5693d67a7e76c9cb9ed9346d82392c9d9a5fe in / 
# Mon, 08 May 2017 23:28:15 GMT
CMD ["/bin/bash"]
# Mon, 08 May 2017 23:53:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 10 May 2017 13:45:41 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Wed, 10 May 2017 13:45:46 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done
# Wed, 10 May 2017 13:45:46 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Wed, 10 May 2017 13:45:47 GMT
ENV NODE_VERSION=4.8.3
# Wed, 10 May 2017 13:46:00 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Mon, 15 May 2017 17:52:48 GMT
ENV YARN_VERSION=0.24.4
# Mon, 15 May 2017 17:52:52 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;   done   && curl -fSL -o yarn.js "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js"   && curl -fSL -o yarn.js.asc "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-legacy-$YARN_VERSION.js.asc"   && gpg --batch --verify yarn.js.asc yarn.js   && rm yarn.js.asc   && mv yarn.js /usr/local/bin/yarn   && chmod +x /usr/local/bin/yarn
# Mon, 15 May 2017 17:52:53 GMT
CMD ["node"]
# Mon, 15 May 2017 19:45:28 GMT
MAINTAINER buildmaster@rocket.chat
# Mon, 15 May 2017 19:45:30 GMT
RUN groupadd -r rocketchat &&  useradd -r -g rocketchat rocketchat &&  mkdir -p /app/uploads &&  chown rocketchat.rocketchat /app/uploads
# Mon, 15 May 2017 19:45:31 GMT
VOLUME [/app/uploads]
# Mon, 15 May 2017 19:45:34 GMT
RUN gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 0E163286C20D07B9787EBE9FD7F9D0414FD08104
# Tue, 16 May 2017 17:48:32 GMT
ENV RC_VERSION=0.56.0
# Tue, 16 May 2017 17:48:33 GMT
WORKDIR /app
# Tue, 16 May 2017 17:49:37 GMT
RUN curl -fSL "https://rocket.chat/releases/${RC_VERSION}/download" -o rocket.chat.tgz &&  curl -fSL "https://rocket.chat/releases/${RC_VERSION}/asc" -o rocket.chat.tgz.asc &&  gpg --batch --verify rocket.chat.tgz.asc rocket.chat.tgz &&  tar zxvf rocket.chat.tgz &&  rm rocket.chat.tgz rocket.chat.tgz.asc &&  cd bundle/programs/server &&  npm install
# Tue, 16 May 2017 17:49:39 GMT
USER [rocketchat]
# Tue, 16 May 2017 17:49:41 GMT
WORKDIR /app/bundle
# Tue, 16 May 2017 17:49:41 GMT
ENV MONGO_URL=mongodb://db:27017/meteor HOME=/tmp PORT=3000 ROOT_URL=http://localhost:3000 Accounts_AvatarStorePath=/app/uploads
# Tue, 16 May 2017 17:49:42 GMT
EXPOSE 3000/tcp
# Tue, 16 May 2017 17:49:43 GMT
CMD ["node" "main.js"]
```

-	Layers:
	-	`sha256:10a267c67f423630f3afe5e04bbbc93d578861ddcc54283526222f3ad5e895b9`  
		Last Modified: Mon, 08 May 2017 23:43:59 GMT  
		Size: 52.6 MB (52584016 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb5937da9414eeab6d68ce06a7ff60d8be1e2c1518ac2588d5df135ab54a9801`  
		Last Modified: Tue, 09 May 2017 15:55:04 GMT  
		Size: 19.3 MB (19267434 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c4b8c9fa331cd6c57e53893f14af4ea47b685786a1144552900e3c47bda5a9b`  
		Last Modified: Sat, 13 May 2017 08:37:01 GMT  
		Size: 4.4 KB (4374 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d31a861b11c6408ac0f77ea0802cbb5bf5024889ed83b82d30c0a4773add657d`  
		Last Modified: Sat, 13 May 2017 08:37:01 GMT  
		Size: 119.2 KB (119154 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9804e730eeb561f017cb2cb0241d3d35ae467dffbb8b12408044678e5da0722d`  
		Last Modified: Sat, 13 May 2017 08:37:06 GMT  
		Size: 12.6 MB (12577882 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c0ea7226ae5d42562ea1300f0c1c40329ea717f48f9c5a465559f528ef95dae7`  
		Last Modified: Mon, 15 May 2017 18:21:59 GMT  
		Size: 895.3 KB (895324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e9bcf8b071d5b09e85241594506488b798bb22b338132b3e26dcec35522e525`  
		Last Modified: Mon, 15 May 2017 20:03:36 GMT  
		Size: 2.2 KB (2155 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48dde9504c3816616edc1f5e756a72c791e0c46137d7b2ea02fc891968eebad1`  
		Last Modified: Mon, 15 May 2017 20:03:36 GMT  
		Size: 127.2 KB (127205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c909f14c3472b92eaaa4173fed82268a4cd7d9ce2bed5b8e9b9d9babe1aea6cd`  
		Last Modified: Tue, 16 May 2017 17:54:16 GMT  
		Size: 115.7 MB (115744236 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
