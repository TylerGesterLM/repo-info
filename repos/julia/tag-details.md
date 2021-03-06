<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `julia`

-	[`julia:0`](#julia0)
-	[`julia:0.6`](#julia06)
-	[`julia:0.6.2`](#julia062)
-	[`julia:latest`](#julialatest)

## `julia:0`

```console
$ docker pull julia@sha256:86dc632739f544a0314b58d50d23abb3358b062059e7fb515be07d09621160e6
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386

### `julia:0` - linux; amd64

```console
$ docker pull julia@sha256:b7016c4f6dc365f59e4549b6d30cc7c2c7e42f372a958fb5748c7af69bfb0c82
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.3 MB (128344280 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ed9a187f7b2124ddb4f786fc1f2773f65d9d80355942cc248083b50dcacf793`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Tue, 01 May 2018 07:51:55 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 07:51:55 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 07:52:03 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 07:52:03 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 07:52:04 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5411096dfd7d336481a27872ed23e3cc959e1f5b5194242489dce7bb1e5e628`  
		Last Modified: Tue, 01 May 2018 07:52:35 GMT  
		Size: 5.1 MB (5069014 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e34c2c6923ecab08f8e3d67f847e7df3c77a809894f5b987345271a6f9f78910`  
		Last Modified: Tue, 01 May 2018 07:52:48 GMT  
		Size: 69.0 MB (69012700 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0` - linux; arm variant v7

```console
$ docker pull julia@sha256:a210e20785941bb8d1eed0693b0db728b254a81e05c9350b1bce16a3616b5b96
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **116.0 MB (116045887 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c4730d82275c0699c14b4266a0439e45d4abc29bb057dc8c9d0971d544a4d2eb`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 13:44:12 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 13:44:14 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 13:44:37 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 13:44:38 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 13:44:38 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:875538f39d331d8270133af48402c5aff1c83fd56962ab835d906e7c361fc870`  
		Last Modified: Sat, 28 Apr 2018 13:45:04 GMT  
		Size: 4.6 MB (4589098 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9be60bc7eda00d7f31b395e4044f64cbf0b9ccd32a5e96d6dba479fe37be95d0`  
		Last Modified: Sat, 28 Apr 2018 13:45:24 GMT  
		Size: 61.3 MB (61261092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0` - linux; arm64 variant v8

```console
$ docker pull julia@sha256:ad71502b3a9f957ce4d1dc1c355408ecec42bab745f7e64bec6a7eb09702ac9b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **115.7 MB (115667740 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:268e908d7fa9cf568d1f05ae575d492c3d356ea0189e1be613543e97e3c266ce`
-	Default Command: `["julia"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 12:03:26 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 12:03:27 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 12:03:28 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 12:03:29 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 12:04:24 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 12:04:25 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 12:04:26 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dc2c04261bb96dc26238aee03fe6290936c27a0e832012b2894bc6dca4ecd7b6`  
		Last Modified: Tue, 01 May 2018 12:04:45 GMT  
		Size: 4.7 MB (4728203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c6f1ad5a4f865e3baffb65bf547069e9c24caa3244fa990cde0d7dd34ef495d`  
		Last Modified: Tue, 01 May 2018 12:05:08 GMT  
		Size: 59.5 MB (59492683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0` - linux; 386

```console
$ docker pull julia@sha256:6d9e3bc4d24c280e5c4077e5ba8d2368ed36967eff7427a468afd5429eb6757f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.8 MB (128776679 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5c7737671790424a38d769b41f76b9a1fa5c44b9ff310b9f3f8d253f499f8bda`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 12:57:21 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 12:57:32 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 12:57:32 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 12:57:32 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6559fde6c859cb3e1a70e9e4599afa2afb56ba9ce6bbca8f3544d9a4650f9c1d`  
		Last Modified: Sat, 28 Apr 2018 12:57:44 GMT  
		Size: 7.2 MB (7235179 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6901de9c3eeb19f78fb83b3acc10019e28643c2b7905ea78406fe6f752761208`  
		Last Modified: Sat, 28 Apr 2018 12:58:01 GMT  
		Size: 67.1 MB (67054718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `julia:0.6`

```console
$ docker pull julia@sha256:86dc632739f544a0314b58d50d23abb3358b062059e7fb515be07d09621160e6
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386

### `julia:0.6` - linux; amd64

```console
$ docker pull julia@sha256:b7016c4f6dc365f59e4549b6d30cc7c2c7e42f372a958fb5748c7af69bfb0c82
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.3 MB (128344280 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ed9a187f7b2124ddb4f786fc1f2773f65d9d80355942cc248083b50dcacf793`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Tue, 01 May 2018 07:51:55 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 07:51:55 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 07:52:03 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 07:52:03 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 07:52:04 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5411096dfd7d336481a27872ed23e3cc959e1f5b5194242489dce7bb1e5e628`  
		Last Modified: Tue, 01 May 2018 07:52:35 GMT  
		Size: 5.1 MB (5069014 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e34c2c6923ecab08f8e3d67f847e7df3c77a809894f5b987345271a6f9f78910`  
		Last Modified: Tue, 01 May 2018 07:52:48 GMT  
		Size: 69.0 MB (69012700 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0.6` - linux; arm variant v7

```console
$ docker pull julia@sha256:a210e20785941bb8d1eed0693b0db728b254a81e05c9350b1bce16a3616b5b96
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **116.0 MB (116045887 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c4730d82275c0699c14b4266a0439e45d4abc29bb057dc8c9d0971d544a4d2eb`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 13:44:12 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 13:44:14 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 13:44:37 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 13:44:38 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 13:44:38 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:875538f39d331d8270133af48402c5aff1c83fd56962ab835d906e7c361fc870`  
		Last Modified: Sat, 28 Apr 2018 13:45:04 GMT  
		Size: 4.6 MB (4589098 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9be60bc7eda00d7f31b395e4044f64cbf0b9ccd32a5e96d6dba479fe37be95d0`  
		Last Modified: Sat, 28 Apr 2018 13:45:24 GMT  
		Size: 61.3 MB (61261092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0.6` - linux; arm64 variant v8

```console
$ docker pull julia@sha256:ad71502b3a9f957ce4d1dc1c355408ecec42bab745f7e64bec6a7eb09702ac9b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **115.7 MB (115667740 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:268e908d7fa9cf568d1f05ae575d492c3d356ea0189e1be613543e97e3c266ce`
-	Default Command: `["julia"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 12:03:26 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 12:03:27 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 12:03:28 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 12:03:29 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 12:04:24 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 12:04:25 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 12:04:26 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dc2c04261bb96dc26238aee03fe6290936c27a0e832012b2894bc6dca4ecd7b6`  
		Last Modified: Tue, 01 May 2018 12:04:45 GMT  
		Size: 4.7 MB (4728203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c6f1ad5a4f865e3baffb65bf547069e9c24caa3244fa990cde0d7dd34ef495d`  
		Last Modified: Tue, 01 May 2018 12:05:08 GMT  
		Size: 59.5 MB (59492683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0.6` - linux; 386

```console
$ docker pull julia@sha256:6d9e3bc4d24c280e5c4077e5ba8d2368ed36967eff7427a468afd5429eb6757f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.8 MB (128776679 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5c7737671790424a38d769b41f76b9a1fa5c44b9ff310b9f3f8d253f499f8bda`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 12:57:21 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 12:57:32 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 12:57:32 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 12:57:32 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6559fde6c859cb3e1a70e9e4599afa2afb56ba9ce6bbca8f3544d9a4650f9c1d`  
		Last Modified: Sat, 28 Apr 2018 12:57:44 GMT  
		Size: 7.2 MB (7235179 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6901de9c3eeb19f78fb83b3acc10019e28643c2b7905ea78406fe6f752761208`  
		Last Modified: Sat, 28 Apr 2018 12:58:01 GMT  
		Size: 67.1 MB (67054718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `julia:0.6.2`

```console
$ docker pull julia@sha256:86dc632739f544a0314b58d50d23abb3358b062059e7fb515be07d09621160e6
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386

### `julia:0.6.2` - linux; amd64

```console
$ docker pull julia@sha256:b7016c4f6dc365f59e4549b6d30cc7c2c7e42f372a958fb5748c7af69bfb0c82
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.3 MB (128344280 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ed9a187f7b2124ddb4f786fc1f2773f65d9d80355942cc248083b50dcacf793`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Tue, 01 May 2018 07:51:55 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 07:51:55 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 07:52:03 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 07:52:03 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 07:52:04 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5411096dfd7d336481a27872ed23e3cc959e1f5b5194242489dce7bb1e5e628`  
		Last Modified: Tue, 01 May 2018 07:52:35 GMT  
		Size: 5.1 MB (5069014 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e34c2c6923ecab08f8e3d67f847e7df3c77a809894f5b987345271a6f9f78910`  
		Last Modified: Tue, 01 May 2018 07:52:48 GMT  
		Size: 69.0 MB (69012700 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0.6.2` - linux; arm variant v7

```console
$ docker pull julia@sha256:a210e20785941bb8d1eed0693b0db728b254a81e05c9350b1bce16a3616b5b96
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **116.0 MB (116045887 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c4730d82275c0699c14b4266a0439e45d4abc29bb057dc8c9d0971d544a4d2eb`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 13:44:12 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 13:44:14 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 13:44:37 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 13:44:38 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 13:44:38 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:875538f39d331d8270133af48402c5aff1c83fd56962ab835d906e7c361fc870`  
		Last Modified: Sat, 28 Apr 2018 13:45:04 GMT  
		Size: 4.6 MB (4589098 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9be60bc7eda00d7f31b395e4044f64cbf0b9ccd32a5e96d6dba479fe37be95d0`  
		Last Modified: Sat, 28 Apr 2018 13:45:24 GMT  
		Size: 61.3 MB (61261092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0.6.2` - linux; arm64 variant v8

```console
$ docker pull julia@sha256:ad71502b3a9f957ce4d1dc1c355408ecec42bab745f7e64bec6a7eb09702ac9b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **115.7 MB (115667740 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:268e908d7fa9cf568d1f05ae575d492c3d356ea0189e1be613543e97e3c266ce`
-	Default Command: `["julia"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 12:03:26 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 12:03:27 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 12:03:28 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 12:03:29 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 12:04:24 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 12:04:25 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 12:04:26 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dc2c04261bb96dc26238aee03fe6290936c27a0e832012b2894bc6dca4ecd7b6`  
		Last Modified: Tue, 01 May 2018 12:04:45 GMT  
		Size: 4.7 MB (4728203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c6f1ad5a4f865e3baffb65bf547069e9c24caa3244fa990cde0d7dd34ef495d`  
		Last Modified: Tue, 01 May 2018 12:05:08 GMT  
		Size: 59.5 MB (59492683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:0.6.2` - linux; 386

```console
$ docker pull julia@sha256:6d9e3bc4d24c280e5c4077e5ba8d2368ed36967eff7427a468afd5429eb6757f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.8 MB (128776679 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5c7737671790424a38d769b41f76b9a1fa5c44b9ff310b9f3f8d253f499f8bda`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 12:57:21 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 12:57:32 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 12:57:32 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 12:57:32 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6559fde6c859cb3e1a70e9e4599afa2afb56ba9ce6bbca8f3544d9a4650f9c1d`  
		Last Modified: Sat, 28 Apr 2018 12:57:44 GMT  
		Size: 7.2 MB (7235179 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6901de9c3eeb19f78fb83b3acc10019e28643c2b7905ea78406fe6f752761208`  
		Last Modified: Sat, 28 Apr 2018 12:58:01 GMT  
		Size: 67.1 MB (67054718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `julia:latest`

```console
$ docker pull julia@sha256:86dc632739f544a0314b58d50d23abb3358b062059e7fb515be07d09621160e6
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386

### `julia:latest` - linux; amd64

```console
$ docker pull julia@sha256:b7016c4f6dc365f59e4549b6d30cc7c2c7e42f372a958fb5748c7af69bfb0c82
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.3 MB (128344280 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ed9a187f7b2124ddb4f786fc1f2773f65d9d80355942cc248083b50dcacf793`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Tue, 01 May 2018 07:51:55 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 07:51:55 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 07:51:56 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 07:52:03 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 07:52:03 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 07:52:04 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5411096dfd7d336481a27872ed23e3cc959e1f5b5194242489dce7bb1e5e628`  
		Last Modified: Tue, 01 May 2018 07:52:35 GMT  
		Size: 5.1 MB (5069014 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e34c2c6923ecab08f8e3d67f847e7df3c77a809894f5b987345271a6f9f78910`  
		Last Modified: Tue, 01 May 2018 07:52:48 GMT  
		Size: 69.0 MB (69012700 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:latest` - linux; arm variant v7

```console
$ docker pull julia@sha256:a210e20785941bb8d1eed0693b0db728b254a81e05c9350b1bce16a3616b5b96
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **116.0 MB (116045887 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c4730d82275c0699c14b4266a0439e45d4abc29bb057dc8c9d0971d544a4d2eb`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 13:44:12 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 13:44:13 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 13:44:14 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 13:44:37 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 13:44:38 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 13:44:38 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:875538f39d331d8270133af48402c5aff1c83fd56962ab835d906e7c361fc870`  
		Last Modified: Sat, 28 Apr 2018 13:45:04 GMT  
		Size: 4.6 MB (4589098 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9be60bc7eda00d7f31b395e4044f64cbf0b9ccd32a5e96d6dba479fe37be95d0`  
		Last Modified: Sat, 28 Apr 2018 13:45:24 GMT  
		Size: 61.3 MB (61261092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:latest` - linux; arm64 variant v8

```console
$ docker pull julia@sha256:ad71502b3a9f957ce4d1dc1c355408ecec42bab745f7e64bec6a7eb09702ac9b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **115.7 MB (115667740 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:268e908d7fa9cf568d1f05ae575d492c3d356ea0189e1be613543e97e3c266ce`
-	Default Command: `["julia"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 12:03:26 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 12:03:27 GMT
ENV JULIA_PATH=/usr/local/julia
# Tue, 01 May 2018 12:03:28 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Tue, 01 May 2018 12:03:29 GMT
ENV JULIA_VERSION=0.6.2
# Tue, 01 May 2018 12:04:24 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Tue, 01 May 2018 12:04:25 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 01 May 2018 12:04:26 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dc2c04261bb96dc26238aee03fe6290936c27a0e832012b2894bc6dca4ecd7b6`  
		Last Modified: Tue, 01 May 2018 12:04:45 GMT  
		Size: 4.7 MB (4728203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c6f1ad5a4f865e3baffb65bf547069e9c24caa3244fa990cde0d7dd34ef495d`  
		Last Modified: Tue, 01 May 2018 12:05:08 GMT  
		Size: 59.5 MB (59492683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `julia:latest` - linux; 386

```console
$ docker pull julia@sha256:6d9e3bc4d24c280e5c4077e5ba8d2368ed36967eff7427a468afd5429eb6757f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.8 MB (128776679 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5c7737671790424a38d769b41f76b9a1fa5c44b9ff310b9f3f8d253f499f8bda`
-	Default Command: `["julia"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 12:57:21 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		curl 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_PATH=/usr/local/julia
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_GPG=3673DF529D9049477F76B37566E3C7DC03D6E495
# Sat, 28 Apr 2018 12:57:22 GMT
ENV JULIA_VERSION=0.6.2
# Sat, 28 Apr 2018 12:57:32 GMT
RUN set -ex; 		dpkgArch="$(dpkg --print-architecture)"; 	case "${dpkgArch##*-}" in 		amd64) tarArch='x86_64'; dirArch='x64'; sha256='dc6ec0b13551ce78083a5849268b20684421d46a7ec46b17ec1fab88a5078580' ;; 		armhf) tarArch='armv7l'; dirArch='armv7l'; sha256='1c37aa7cba7372d949a91de53f53609b1b0c9cbeca436eb2fe7f5083d9f62c82' ;; 		arm64) tarArch='aarch64'; dirArch='aarch64'; sha256='19a8945bdb3d35b7bf0432a9e066fb7831d11d1c1acfe56abd8fcabbf1ebddb4' ;; 		i386) tarArch='i686'; dirArch='x86'; sha256='099e39ad958aff2ef63841a812f5df62f8553aafc6dd33abb0eb0c67142c5e49' ;; 		*) echo >&2 "error: current architecture ($dpkgArch) does not have a corresponding Julia binary release"; exit 1 ;; 	esac; 		curl -fL -o julia.tar.gz     "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz"; 	curl -fL -o julia.tar.gz.asc "https://julialang-s3.julialang.org/bin/linux/${dirArch}/${JULIA_VERSION%[.-]*}/julia-${JULIA_VERSION}-linux-${tarArch}.tar.gz.asc"; 		echo "${sha256} *julia.tar.gz" | sha256sum -c -; 		export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$JULIA_GPG"; 	gpg --batch --verify julia.tar.gz.asc julia.tar.gz; 	rm -rf "$GNUPGHOME" julia.tar.gz.asc; 		mkdir "$JULIA_PATH"; 	tar -xzf julia.tar.gz -C "$JULIA_PATH" --strip-components 1; 	rm julia.tar.gz
# Sat, 28 Apr 2018 12:57:32 GMT
ENV PATH=/usr/local/julia/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 28 Apr 2018 12:57:32 GMT
CMD ["julia"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6559fde6c859cb3e1a70e9e4599afa2afb56ba9ce6bbca8f3544d9a4650f9c1d`  
		Last Modified: Sat, 28 Apr 2018 12:57:44 GMT  
		Size: 7.2 MB (7235179 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6901de9c3eeb19f78fb83b3acc10019e28643c2b7905ea78406fe6f752761208`  
		Last Modified: Sat, 28 Apr 2018 12:58:01 GMT  
		Size: 67.1 MB (67054718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
