## `buildpack-deps:bionic-scm`

```console
$ docker pull buildpack-deps@sha256:0db016698e783d869aed4ce9428fc3e5729656c64d7cd9efd87c7307cca0f6e7
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7

### `buildpack-deps:bionic-scm` - linux; amd64

```console
$ docker pull buildpack-deps@sha256:1840c291d082f990ca4d48963db414da79c5c70ef508b35992a8d741937d44f0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **89.8 MB (89812324 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9b5247bb5d8e5f129862c08125f494304904edffdc6db2ae830d5a136fc1258b`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Fri, 17 Nov 2017 21:58:49 GMT
ADD file:4f66e9d880cdde359f64c9423bebfcb08662b30c4ef8042b019c1270d311b308 in / 
# Fri, 17 Nov 2017 21:58:50 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 17 Nov 2017 21:58:50 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 17 Nov 2017 21:58:51 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 17 Nov 2017 21:58:51 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 17 Nov 2017 21:58:52 GMT
CMD ["/bin/bash"]
# Sat, 09 Dec 2017 01:41:41 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 09 Dec 2017 01:41:42 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 09 Dec 2017 01:42:12 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
```

-	Layers:
	-	`sha256:e1431537f6d312c5ed238e1116b2f63ad47203ad5e03f695391a00f75517efb1`  
		Last Modified: Fri, 17 Nov 2017 22:00:28 GMT  
		Size: 36.0 MB (36017823 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e318c3f4b1de94a78950d4a6fc7682515062b41f7d2b0deeb866073060b0da0`  
		Last Modified: Fri, 17 Nov 2017 22:00:23 GMT  
		Size: 839.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a77eaecc130c6c13106780b5d18192fd5241c4162e3f7f06e3b0bdc6ed92160d`  
		Last Modified: Fri, 17 Nov 2017 22:00:23 GMT  
		Size: 395.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43d315640310c8f2e6d3a6abcd779e58dd5fa228d5fddb4d966efe3cdb9a87c3`  
		Last Modified: Fri, 17 Nov 2017 22:00:23 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02830adeac1de366c6d5e1da708225efb5749ced0799898d2a715c680ee6294f`  
		Last Modified: Fri, 17 Nov 2017 22:00:23 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b0048ac95e0e0cfa55c6fa6022f7faf730575c8915d2ad117459e07885ba21b`  
		Last Modified: Sat, 09 Dec 2017 01:45:04 GMT  
		Size: 6.1 MB (6058588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de00f9b86b7daaa29d8b19a0bd083c6279cd56daa2e5ae72e32986983a7f1293`  
		Last Modified: Sat, 09 Dec 2017 01:45:32 GMT  
		Size: 47.7 MB (47733664 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:bionic-scm` - linux; arm variant v7

```console
$ docker pull buildpack-deps@sha256:a2ccb3361d0abba537d53cfd45cafdea1e1a9839d4bf0f02e7f999a733084a2e
```

-	Docker Version: 17.06.0-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **80.8 MB (80785340 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0ebc67973cc6b95429e0db2566177491466e2169ba22f945b97937b6917da28`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Fri, 17 Nov 2017 22:08:18 GMT
ADD file:bcd586ce20c40eb5dc1f34cbdc2604e88966ea683538604a7e65c1fa494b33f4 in / 
# Fri, 17 Nov 2017 22:08:19 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Fri, 17 Nov 2017 22:08:20 GMT
RUN rm -rf /var/lib/apt/lists/*
# Fri, 17 Nov 2017 22:08:21 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Fri, 17 Nov 2017 22:08:22 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Fri, 17 Nov 2017 22:08:22 GMT
CMD ["/bin/bash"]
# Sat, 09 Dec 2017 01:08:15 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 09 Dec 2017 01:08:16 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 09 Dec 2017 01:09:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
```

-	Layers:
	-	`sha256:c5c8ac4ce78715b00ba2a37425fc0ab448770d8f5af1ec19a4ee2cc9dc9c8c84`  
		Last Modified: Fri, 17 Nov 2017 22:11:16 GMT  
		Size: 31.9 MB (31940819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f9c76382cb7292a13e059c2b786f8aa51eaee4113ddb7331be408ea3df3fb20`  
		Last Modified: Fri, 17 Nov 2017 22:11:07 GMT  
		Size: 844.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b3b689d6fdf4b35646aef0f54505bd063ba21ace4509f40ca2897ca308ef1461`  
		Last Modified: Fri, 17 Nov 2017 22:11:07 GMT  
		Size: 390.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:123e3273c208fc7f247854196cdc614c2815d630a3304f5126ba701e8416161b`  
		Last Modified: Fri, 17 Nov 2017 22:11:07 GMT  
		Size: 852.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5771861c30634ae881f8bd31e0def38e619896e9cc84e1e0c35c05a939b927d4`  
		Last Modified: Fri, 17 Nov 2017 22:11:08 GMT  
		Size: 188.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa38424712fe39a305b5c4a07f752000fe9a9e781b8204bb962a7318cbac77a9`  
		Last Modified: Sat, 09 Dec 2017 01:12:38 GMT  
		Size: 5.1 MB (5098547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fef9d1e65fb91cec0301dc43ad1334865243dc15e6daf687d6472e85fa58c0aa`  
		Last Modified: Sat, 09 Dec 2017 01:13:04 GMT  
		Size: 43.7 MB (43743700 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip