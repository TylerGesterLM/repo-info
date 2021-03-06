## `jetty:jre7`

```console
$ docker pull jetty@sha256:45cbaa25cf35fb00772c79b4abeb018f3ff95fd576a813b202442eb537457b39
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `jetty:jre7` - linux; amd64

```console
$ docker pull jetty@sha256:f8e845a56e4b2cbf800767015dd63f4805f33a397467859b17f09921653a2507
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **199.7 MB (199719477 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:558856e3422a775201bc03d244ceb1f7bd3a2cfb94aa67d06b2328241efd7216`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Fri, 04 May 2018 17:35:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 04 May 2018 17:35:09 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Fri, 04 May 2018 23:55:07 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Fri, 04 May 2018 23:55:07 GMT
ENV LANG=C.UTF-8
# Fri, 04 May 2018 23:55:08 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 04 May 2018 23:55:09 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Fri, 04 May 2018 23:55:09 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Fri, 04 May 2018 23:55:10 GMT
ENV JAVA_VERSION=7u171
# Fri, 04 May 2018 23:55:10 GMT
ENV JAVA_DEBIAN_VERSION=7u171-2.6.13-1~deb8u1
# Fri, 04 May 2018 23:56:16 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 05 May 2018 08:23:43 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Sat, 05 May 2018 08:23:43 GMT
ENV JETTY_HOME=/usr/local/jetty
# Sat, 05 May 2018 08:23:43 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 05 May 2018 08:23:44 GMT
RUN mkdir -p "$JETTY_HOME"
# Sat, 05 May 2018 08:23:44 GMT
WORKDIR /usr/local/jetty
# Sat, 05 May 2018 08:23:44 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Sat, 05 May 2018 08:23:45 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Sat, 05 May 2018 08:23:45 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Sat, 05 May 2018 08:23:47 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Sat, 05 May 2018 08:23:48 GMT
ENV JETTY_BASE=/var/lib/jetty
# Sat, 05 May 2018 08:23:48 GMT
RUN mkdir -p "$JETTY_BASE"
# Sat, 05 May 2018 08:23:49 GMT
WORKDIR /var/lib/jetty
# Sat, 05 May 2018 08:23:52 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Sat, 05 May 2018 08:23:52 GMT
ENV TMPDIR=/tmp/jetty
# Sat, 05 May 2018 08:23:53 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Sat, 05 May 2018 08:23:53 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Sat, 05 May 2018 08:23:54 GMT
USER [jetty]
# Sat, 05 May 2018 08:23:54 GMT
EXPOSE 8080/tcp
# Sat, 05 May 2018 08:23:54 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 05 May 2018 08:23:54 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:534514c83d698ad8a2ef994eeedaed92738e401d735e453d47e635cca02901b6`  
		Last Modified: Fri, 04 May 2018 18:19:14 GMT  
		Size: 17.6 MB (17584745 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1fa6a9b010fb612341f299da8a75e0b1c8f76b9a2b22ff64b7efafb03d14c70f`  
		Last Modified: Sat, 05 May 2018 00:13:02 GMT  
		Size: 795.4 KB (795371 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90941e5e9ceaabf5ba0200f1004c55f862814c7c117443937de540ef799f33a9`  
		Last Modified: Sat, 05 May 2018 00:13:01 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49caad7cc7de95b56a92c570322318fc89f41759cbba41942187d0a82348f68e`  
		Last Modified: Sat, 05 May 2018 00:13:01 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a59df1c6a06a48c5b1e95dd82a47f0e272651e65e5ba59e3049416e328faa83`  
		Last Modified: Sat, 05 May 2018 00:13:20 GMT  
		Size: 117.0 MB (117042177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a4372ba35aac0f1ed199256a6fa88eb6ebe24bd1327acf65641696fe3be13c2`  
		Last Modified: Sat, 05 May 2018 08:25:59 GMT  
		Size: 2.2 KB (2152 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5724f977f7445aed11837b48724eaea43e0ba23f1372c74814ae443a8fca9513`  
		Last Modified: Sat, 05 May 2018 08:25:58 GMT  
		Size: 151.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76b1233cab47a6c9b91fe3d1176ca402ab75ded66444f79b50dbf645ae67a513`  
		Last Modified: Sat, 05 May 2018 08:25:57 GMT  
		Size: 10.0 MB (10028814 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8783e1e0a84c1db8de2f8e99a4a04650d5928b113a27d27c13c22aa8047d1ba`  
		Last Modified: Sat, 05 May 2018 08:25:56 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25e29333561b525d3d6c5468cefe50f3854d148b8a576e86eadefcd724811720`  
		Last Modified: Sat, 05 May 2018 08:25:56 GMT  
		Size: 1.5 KB (1472 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13fe5737209d4fed4ea308390529150d254fedaebe9eb2a3d762c0f5d2fb2d53`  
		Last Modified: Sat, 05 May 2018 08:25:58 GMT  
		Size: 127.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e813afa4682e2fac0bb6e6981f7ac9b3568ec8c1f407357ecc21e0f2248fffc`  
		Last Modified: Sat, 05 May 2018 08:25:56 GMT  
		Size: 1.4 KB (1386 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
