## `adminer:4-standalone`

```console
$ docker pull adminer@sha256:58a1c381f438ba321ec1971629e714cbe9921908dc3245e5db5753357117ded5
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le

### `adminer:4-standalone` - linux; amd64

```console
$ docker pull adminer@sha256:4c21fc62de8037b7fbaf9f40f5fdaf6103741eb14074e0ff0a9d612bfdf40aad
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **29.2 MB (29238806 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6faa90365dab5b01bbd63cb379ece73feaccf2525a74ad22d4530551bddd0a25`
-	Entrypoint: `["entrypoint.sh","docker-php-entrypoint"]`
-	Default Command: `["php","-S","[::]:8080","-t","\/var\/www\/html"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:38 GMT
ADD file:6edc55fb54ec9fc3658c8f5176a70e792103a516154442f94fed8e0290e4960e in / 
# Tue, 09 Jan 2018 21:10:38 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 02:16:45 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Wed, 10 Jan 2018 02:16:48 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Wed, 10 Jan 2018 02:16:57 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Wed, 10 Jan 2018 02:16:57 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Wed, 10 Jan 2018 02:16:58 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Wed, 10 Jan 2018 02:16:58 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 10 Jan 2018 02:16:58 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 10 Jan 2018 02:16:58 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Wed, 10 Jan 2018 02:16:58 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Fri, 27 Apr 2018 01:56:01 GMT
ENV PHP_VERSION=7.2.5
# Fri, 27 Apr 2018 01:56:01 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.5.tar.xz.asc/from/this/mirror
# Fri, 27 Apr 2018 01:56:02 GMT
ENV PHP_SHA256=af70a33b3f7a51510467199b39af151333fbbe4cc21923bad9c7cf64268cddb2 PHP_MD5=
# Fri, 27 Apr 2018 01:56:12 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Fri, 27 Apr 2018 01:56:12 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 05 May 2018 00:55:58 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--disable-cgi 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 05 May 2018 00:55:59 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 05 May 2018 00:56:00 GMT
RUN docker-php-ext-enable sodium
# Sat, 05 May 2018 00:56:00 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 05 May 2018 00:56:00 GMT
CMD ["php" "-a"]
# Sat, 05 May 2018 12:09:42 GMT
STOPSIGNAL [SIGINT]
# Sat, 05 May 2018 12:09:43 GMT
RUN addgroup -S adminer &&	adduser -S -G adminer adminer &&	mkdir -p /var/www/html &&	mkdir -p /var/www/html/plugins-enabled &&	chown -R adminer:adminer /var/www/html
# Sat, 05 May 2018 12:09:43 GMT
WORKDIR /var/www/html
# Sat, 05 May 2018 12:09:44 GMT
RUN apk add --no-cache libpq
# Sat, 05 May 2018 12:09:59 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 	postgresql-dev 	sqlite-dev &&	docker-php-ext-install pdo_mysql pdo_pgsql pdo_sqlite &&	apk del .build-deps
# Sat, 05 May 2018 12:09:59 GMT
COPY multi:fcdffffd48fc0fc7ad3b317e64231ca1b160ab11eac6289d64ba2a4bdfd85ccc in /var/www/html/ 
# Sat, 05 May 2018 12:09:59 GMT
ENV ADMINER_VERSION=4.6.2
# Wed, 09 May 2018 16:57:04 GMT
ENV ADMINER_DOWNLOAD_SHA256=2b3e5e87ed1214288378fc272c1ba0497ec2f1128444e3a581eabd435f5575b9
# Wed, 09 May 2018 16:57:04 GMT
ENV ADMINER_SRC_DOWNLOAD_SHA256=13f26a5aeed2f734d9309a922592f2e2b35ba2ea5c1c2a2c8402ca26a8808682
# Wed, 09 May 2018 16:57:08 GMT
RUN set -x &&	curl -fsSL https://github.com/vrana/adminer/releases/download/v$ADMINER_VERSION/adminer-$ADMINER_VERSION.php -o adminer.php &&	echo "$ADMINER_DOWNLOAD_SHA256  adminer.php" |sha256sum -c - &&	curl -fsSL https://github.com/vrana/adminer/archive/v$ADMINER_VERSION.tar.gz -o source.tar.gz &&	echo "$ADMINER_SRC_DOWNLOAD_SHA256  source.tar.gz" |sha256sum -c - &&	tar xzf source.tar.gz --strip-components=1 "adminer-$ADMINER_VERSION/designs/" "adminer-$ADMINER_VERSION/plugins/" &&	rm source.tar.gz
# Wed, 09 May 2018 16:57:08 GMT
COPY file:7d0b9a0787be28f6522891c0b9e7249e1c7d88759916642b95d9d3296ed72be5 in /usr/local/bin/ 
# Wed, 09 May 2018 16:57:08 GMT
ENTRYPOINT ["entrypoint.sh" "docker-php-entrypoint"]
# Wed, 09 May 2018 16:57:08 GMT
USER [adminer]
# Wed, 09 May 2018 16:57:08 GMT
CMD ["php" "-S" "[::]:8080" "-t" "/var/www/html"]
# Wed, 09 May 2018 16:57:09 GMT
EXPOSE 8080/tcp
```

-	Layers:
	-	`sha256:605ce1bd3f3164f2949a30501cc596f52a72de05da1306ab360055f0d7130c32`  
		Last Modified: Tue, 09 Jan 2018 21:13:17 GMT  
		Size: 2.0 MB (1991747 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f5aa494661d4ce499e894e1ff4107c24fa7d5ccb23bf1e3c8240f547a9c3993`  
		Last Modified: Wed, 10 Jan 2018 04:31:15 GMT  
		Size: 1.4 MB (1386596 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7963c90c835a47aacef9a89e2028103b267818e84b69293ce2045917158a6ba5`  
		Last Modified: Wed, 10 Jan 2018 04:31:15 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3f2a1640434671ac201f14d75ba5a18a2869bf2882f9e25afd23767c8ea61b0`  
		Last Modified: Wed, 10 Jan 2018 04:31:12 GMT  
		Size: 169.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fea75f93b921e4ec9bf74cc1dc4514405562e02561706042defb2a38ed94d0c6`  
		Last Modified: Fri, 27 Apr 2018 05:23:37 GMT  
		Size: 12.1 MB (12054187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c1706f3744ae972340a9d93ed62372285c182a4fc9a01b7a34316fffc763dec0`  
		Last Modified: Fri, 27 Apr 2018 05:23:35 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e597b2d0faa7b3d577de61a55fe09613a42f504ef97b509ff3353f19166c8350`  
		Last Modified: Sat, 05 May 2018 02:35:26 GMT  
		Size: 11.9 MB (11895188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c39068308fce6b97e13e063a7f5accf5fb7ed35bfdf34c0b185a5dc4d0d59539`  
		Last Modified: Sat, 05 May 2018 02:35:24 GMT  
		Size: 2.2 KB (2168 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e17d462103b0a65dfcab04b4609a1ba14a33cd66e6b8c6e31b82c083dbf9b4fe`  
		Last Modified: Sat, 05 May 2018 02:35:24 GMT  
		Size: 71.1 KB (71103 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5c3ce2110c2d700a593423321fa5d3d5282bae5e82d4ef168e62d73fbb78729`  
		Last Modified: Sat, 05 May 2018 12:12:05 GMT  
		Size: 1.4 KB (1358 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:882fd73fb5604c3ef8ca16ed117787add2f835120cf452ceab787b15d57a0fb0`  
		Last Modified: Sat, 05 May 2018 12:12:04 GMT  
		Size: 1.2 MB (1209140 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ece1f5b93f039eac801c8e7f7ec2abb5520214109ba516607a3cf74176ebbfd8`  
		Last Modified: Sat, 05 May 2018 12:12:05 GMT  
		Size: 120.5 KB (120454 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7fc7cbeecaa24b2cf4cc5fe5275dd34c13e9b412afaddd7f35f26830734ee8c`  
		Last Modified: Sat, 05 May 2018 12:12:03 GMT  
		Size: 1.5 KB (1463 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e96ef2ddd43047cbcaa08776111c6c2ab6139595233f336017f76d4da498dffb`  
		Last Modified: Wed, 09 May 2018 16:57:29 GMT  
		Size: 503.0 KB (502986 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6cfcd2e73015a5a68fccdd46d023b7fb35cd30faa3d6acb858f9b1702040a76`  
		Last Modified: Wed, 09 May 2018 16:57:28 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `adminer:4-standalone` - linux; arm variant v6

```console
$ docker pull adminer@sha256:526001ab5ee5bdca5f01e6b18ecda0877fa756eb6d7db44a8ffc01fc39323dd3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **29.4 MB (29416623 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5ccccfc709412bb67a058e73a1f6daa4fe817206f84d58269dc05539ff660cfb`
-	Entrypoint: `["entrypoint.sh","docker-php-entrypoint"]`
-	Default Command: `["php","-S","[::]:8080","-t","\/var\/www\/html"]`

```dockerfile
# Wed, 25 Oct 2017 23:28:35 GMT
ADD file:009348222efb3c4ca2e53c387fb34c488679ca07db39525a6c5cc214e46abffd in / 
# Wed, 25 Oct 2017 23:28:36 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 25 Oct 2017 23:28:36 GMT
CMD ["/bin/sh"]
# Fri, 01 Dec 2017 06:16:24 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Dec 2017 06:16:28 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Dec 2017 06:16:29 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Dec 2017 06:16:29 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Dec 2017 06:16:30 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Dec 2017 06:16:30 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 06:16:30 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 06:16:30 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Dec 2017 06:16:31 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Tue, 09 Jan 2018 06:26:21 GMT
ENV PHP_VERSION=7.2.1
# Tue, 09 Jan 2018 06:26:22 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.1.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.1.tar.xz.asc/from/this/mirror
# Tue, 09 Jan 2018 06:26:22 GMT
ENV PHP_SHA256=6c6cf82fda6660ed963821eb0525214bb3547e8e29f447b9c15b2d8e6efd8822 PHP_MD5=
# Tue, 09 Jan 2018 06:26:36 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Tue, 09 Jan 2018 06:26:37 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Tue, 09 Jan 2018 06:29:34 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Tue, 09 Jan 2018 06:29:35 GMT
COPY multi:0de99b27377ea60c319e566076843370f751e856c1e3a64b2dcd283a35066564 in /usr/local/bin/ 
# Tue, 09 Jan 2018 06:29:35 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Tue, 09 Jan 2018 06:29:35 GMT
CMD ["php" "-a"]
# Tue, 09 Jan 2018 06:53:52 GMT
STOPSIGNAL [SIGINT]
# Tue, 09 Jan 2018 06:53:53 GMT
RUN addgroup -S adminer &&	adduser -S -G adminer adminer &&	mkdir -p /var/www/html &&	mkdir -p /var/www/html/plugins-enabled &&	chown -R adminer:adminer /var/www/html
# Tue, 09 Jan 2018 06:53:53 GMT
WORKDIR /var/www/html
# Tue, 09 Jan 2018 06:53:55 GMT
RUN apk add --no-cache libpq
# Tue, 09 Jan 2018 06:54:21 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 	postgresql-dev 	sqlite-dev &&	docker-php-ext-install pdo_mysql pdo_pgsql pdo_sqlite &&	apk del .build-deps
# Tue, 09 Jan 2018 06:54:21 GMT
COPY multi:fcdffffd48fc0fc7ad3b317e64231ca1b160ab11eac6289d64ba2a4bdfd85ccc in /var/www/html/ 
# Wed, 21 Feb 2018 08:42:24 GMT
ENV ADMINER_VERSION=4.6.2
# Tue, 08 May 2018 07:51:05 GMT
ENV ADMINER_DOWNLOAD_SHA256=2b3e5e87ed1214288378fc272c1ba0497ec2f1128444e3a581eabd435f5575b9
# Tue, 08 May 2018 07:51:05 GMT
ENV ADMINER_SRC_DOWNLOAD_SHA256=13f26a5aeed2f734d9309a922592f2e2b35ba2ea5c1c2a2c8402ca26a8808682
# Tue, 08 May 2018 07:51:07 GMT
RUN set -x &&	curl -fsSL https://github.com/vrana/adminer/releases/download/v$ADMINER_VERSION/adminer-$ADMINER_VERSION.php -o adminer.php &&	echo "$ADMINER_DOWNLOAD_SHA256  adminer.php" |sha256sum -c - &&	curl -fsSL https://github.com/vrana/adminer/archive/v$ADMINER_VERSION.tar.gz -o source.tar.gz &&	echo "$ADMINER_SRC_DOWNLOAD_SHA256  source.tar.gz" |sha256sum -c - &&	tar xzf source.tar.gz --strip-components=1 "adminer-$ADMINER_VERSION/designs/" "adminer-$ADMINER_VERSION/plugins/" &&	rm source.tar.gz
# Tue, 08 May 2018 07:51:07 GMT
COPY file:7d0b9a0787be28f6522891c0b9e7249e1c7d88759916642b95d9d3296ed72be5 in /usr/local/bin/ 
# Tue, 08 May 2018 07:51:07 GMT
ENTRYPOINT ["entrypoint.sh" "docker-php-entrypoint"]
# Tue, 08 May 2018 07:51:08 GMT
USER [adminer]
# Tue, 08 May 2018 07:51:08 GMT
CMD ["php" "-S" "[::]:8080" "-t" "/var/www/html"]
# Tue, 08 May 2018 07:51:08 GMT
EXPOSE 8080/tcp
```

-	Layers:
	-	`sha256:0864efeeb5cb8dca4eb53e5d6fd38486daee80fa326fe36d1ad254f8fa6bb310`  
		Last Modified: Sun, 23 Jul 2017 20:21:42 GMT  
		Size: 2.0 MB (1965988 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cda69762aee1588fa82aeabf1af6d6ad24f737cce1451fab2e0199849b1e12e`  
		Last Modified: Wed, 25 Oct 2017 23:28:45 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:118ab63d4d0efa89919ef1bf2b44f1f272f669567b6c339a05e81742927c4876`  
		Last Modified: Fri, 01 Dec 2017 06:26:42 GMT  
		Size: 1.4 MB (1375467 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfbc800f357a5889e0182fd2de447c9cc7c974dc4bbcc859ff647eb5c3b697a1`  
		Last Modified: Fri, 01 Dec 2017 06:26:41 GMT  
		Size: 1.3 KB (1278 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b254b97c6bcf1ef6f8f2f606984395003acac0f9046d1c7cbe796cd143a66c6d`  
		Last Modified: Fri, 01 Dec 2017 06:26:40 GMT  
		Size: 198.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c58a0b7a113b1162cf001d1383a7dcdc9a76ed83b45a9b8d3dd555868959185d`  
		Last Modified: Tue, 09 Jan 2018 06:37:19 GMT  
		Size: 12.1 MB (12114532 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7baeef689e49811b051c4c479712fc6cdee021fc4818e8efdc52fa2326c376b5`  
		Last Modified: Tue, 09 Jan 2018 06:37:18 GMT  
		Size: 495.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6b4f9ca5dec674abe0d49ab87f5c781200ec55048bd4287814a689cc1f9efca`  
		Last Modified: Tue, 09 Jan 2018 06:37:22 GMT  
		Size: 12.2 MB (12163947 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8cb5a111256db6bc3135c425102bbd127ae80c78565fb4082d232bbe2805c0a3`  
		Last Modified: Tue, 09 Jan 2018 06:37:18 GMT  
		Size: 2.2 KB (2164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1fbc2571f396c321d1ff0975910feafd69b6fd6f021c0f7093a1cc00eed6eee3`  
		Last Modified: Tue, 09 Jan 2018 06:55:15 GMT  
		Size: 1.4 KB (1408 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab33ae237377703678483d09ba8b69df07912174b59b9c9a39d8e2b1d07b6562`  
		Last Modified: Tue, 09 Jan 2018 06:55:14 GMT  
		Size: 1.2 MB (1168743 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa0ca57882b290853d36776d1b4baef2453ea96141b1c7a445a1f2978c5facf7`  
		Last Modified: Tue, 09 Jan 2018 06:55:14 GMT  
		Size: 117.2 KB (117200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61429a2f3a84325b8683e03bc592c06399b43499bb747a47b606f5154dca3a3e`  
		Last Modified: Tue, 09 Jan 2018 06:55:13 GMT  
		Size: 1.5 KB (1464 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75b3e1639e08a0f0ddb52a29f83fbee09306889f24f892b3c37e80e10e0bb87b`  
		Last Modified: Tue, 08 May 2018 07:51:52 GMT  
		Size: 503.1 KB (503070 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:130fcc7f366573b8c37a2bf16178bf74373ca01c816eebad9164c5da3be0e50b`  
		Last Modified: Tue, 08 May 2018 07:51:52 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `adminer:4-standalone` - linux; arm64 variant v8

```console
$ docker pull adminer@sha256:0e38993f9723b5fa3fee6631b35be2764560b4dd843e0bae25999bab4eb2c862
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **29.4 MB (29403513 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:582cba77ad0dc46f16a4735f7105aa458038d48f73026632e4ce9c998bc2c0c9`
-	Entrypoint: `["entrypoint.sh","docker-php-entrypoint"]`
-	Default Command: `["php","-S","[::]:8080","-t","\/var\/www\/html"]`

```dockerfile
# Wed, 25 Oct 2017 23:28:58 GMT
ADD file:45b5d3b8d5490ba7edfca2cf6f54cdcf49c772b0b3a2302ce69a7af061007aa4 in / 
# Wed, 25 Oct 2017 23:28:59 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 25 Oct 2017 23:28:59 GMT
CMD ["/bin/sh"]
# Fri, 01 Dec 2017 03:26:53 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Dec 2017 03:26:58 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Dec 2017 03:27:00 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Dec 2017 03:27:01 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Dec 2017 03:27:02 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Dec 2017 03:27:03 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 03:27:04 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 03:27:04 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Dec 2017 03:27:05 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Tue, 01 May 2018 04:46:33 GMT
ENV PHP_VERSION=7.2.5
# Tue, 01 May 2018 04:46:34 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.5.tar.xz.asc/from/this/mirror
# Tue, 01 May 2018 04:46:34 GMT
ENV PHP_SHA256=af70a33b3f7a51510467199b39af151333fbbe4cc21923bad9c7cf64268cddb2 PHP_MD5=
# Tue, 01 May 2018 04:46:52 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Tue, 01 May 2018 04:46:53 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 05 May 2018 15:16:53 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--disable-cgi 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 05 May 2018 15:16:55 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 05 May 2018 15:16:57 GMT
RUN docker-php-ext-enable sodium
# Sat, 05 May 2018 15:16:58 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 05 May 2018 15:16:59 GMT
CMD ["php" "-a"]
# Sat, 05 May 2018 23:33:03 GMT
STOPSIGNAL [SIGINT]
# Sat, 05 May 2018 23:33:06 GMT
RUN addgroup -S adminer &&	adduser -S -G adminer adminer &&	mkdir -p /var/www/html &&	mkdir -p /var/www/html/plugins-enabled &&	chown -R adminer:adminer /var/www/html
# Sat, 05 May 2018 23:33:09 GMT
WORKDIR /var/www/html
# Sat, 05 May 2018 23:33:13 GMT
RUN apk add --no-cache libpq
# Sat, 05 May 2018 23:33:49 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 	postgresql-dev 	sqlite-dev &&	docker-php-ext-install pdo_mysql pdo_pgsql pdo_sqlite &&	apk del .build-deps
# Sat, 05 May 2018 23:33:51 GMT
COPY multi:fcdffffd48fc0fc7ad3b317e64231ca1b160ab11eac6289d64ba2a4bdfd85ccc in /var/www/html/ 
# Sat, 05 May 2018 23:33:52 GMT
ENV ADMINER_VERSION=4.6.2
# Tue, 08 May 2018 08:39:24 GMT
ENV ADMINER_DOWNLOAD_SHA256=2b3e5e87ed1214288378fc272c1ba0497ec2f1128444e3a581eabd435f5575b9
# Tue, 08 May 2018 08:39:25 GMT
ENV ADMINER_SRC_DOWNLOAD_SHA256=13f26a5aeed2f734d9309a922592f2e2b35ba2ea5c1c2a2c8402ca26a8808682
# Tue, 08 May 2018 08:39:29 GMT
RUN set -x &&	curl -fsSL https://github.com/vrana/adminer/releases/download/v$ADMINER_VERSION/adminer-$ADMINER_VERSION.php -o adminer.php &&	echo "$ADMINER_DOWNLOAD_SHA256  adminer.php" |sha256sum -c - &&	curl -fsSL https://github.com/vrana/adminer/archive/v$ADMINER_VERSION.tar.gz -o source.tar.gz &&	echo "$ADMINER_SRC_DOWNLOAD_SHA256  source.tar.gz" |sha256sum -c - &&	tar xzf source.tar.gz --strip-components=1 "adminer-$ADMINER_VERSION/designs/" "adminer-$ADMINER_VERSION/plugins/" &&	rm source.tar.gz
# Tue, 08 May 2018 08:39:30 GMT
COPY file:7d0b9a0787be28f6522891c0b9e7249e1c7d88759916642b95d9d3296ed72be5 in /usr/local/bin/ 
# Tue, 08 May 2018 08:39:30 GMT
ENTRYPOINT ["entrypoint.sh" "docker-php-entrypoint"]
# Tue, 08 May 2018 08:39:31 GMT
USER [adminer]
# Tue, 08 May 2018 08:39:31 GMT
CMD ["php" "-S" "[::]:8080" "-t" "/var/www/html"]
# Tue, 08 May 2018 08:39:32 GMT
EXPOSE 8080/tcp
```

-	Layers:
	-	`sha256:bb473f0ebc12fde1bd45c1bd3c46f2d3aab367b1b7739464771455b9972f7894`  
		Last Modified: Thu, 06 Jul 2017 09:54:42 GMT  
		Size: 1.9 MB (1914748 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75ff6b7ff3a208b8399e701e7ea1b7edbdc654c8c60d33c6f09a7803e2dda776`  
		Last Modified: Wed, 25 Oct 2017 23:29:45 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7936537e9e8eb421dc1abbe8b7a321784aae49b26ecba40d45684bdae461dc41`  
		Last Modified: Fri, 01 Dec 2017 05:26:21 GMT  
		Size: 1.3 MB (1338713 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:897b867d90e3e314231763652ab368dda9d0595e8b3827d816840cc676c3d6c5`  
		Last Modified: Fri, 01 Dec 2017 05:26:20 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:153f3b68b311cd4ebc798e1e2a26065db5b891e0b2f50e60c3792215927a5853`  
		Last Modified: Fri, 01 Dec 2017 05:26:18 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:710246f37fc17496a092580e9781e22d06e6396ab7f9f328a40d96430a940dc5`  
		Last Modified: Tue, 01 May 2018 07:18:00 GMT  
		Size: 12.1 MB (12054581 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0d594916e94025dd7e2b034cbb92348291bff071dbba62ef619f28c98550ffd`  
		Last Modified: Tue, 01 May 2018 07:17:58 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b8a15f763281f777fe38ab980933f12b743958e64360a8023b72018cd866cde`  
		Last Modified: Sat, 05 May 2018 18:35:36 GMT  
		Size: 12.3 MB (12252874 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3965b6c85e959069d794a18d754ec69f1d203b69eb3483d073b787c07e9da25`  
		Last Modified: Sat, 05 May 2018 18:35:28 GMT  
		Size: 2.2 KB (2171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da988abd78850a4f186963c16e93480b28a920bd3696d3b72c7bd2cf5c722d22`  
		Last Modified: Sat, 05 May 2018 18:35:29 GMT  
		Size: 70.1 KB (70088 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f30b184a24ced059f5b614508a57b48626b03043a0c7fec8719b5e820fffa6b1`  
		Last Modified: Sat, 05 May 2018 23:35:23 GMT  
		Size: 1.4 KB (1363 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a351846d895ac9a2955566bf2ac97f703474e4aee276faabe3938a8a8b18025`  
		Last Modified: Sat, 05 May 2018 23:35:21 GMT  
		Size: 1.1 MB (1144356 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:216c55f4bc3e29326d3349908ccca67616932e753d313c91f184e416565acfc6`  
		Last Modified: Sat, 05 May 2018 23:35:21 GMT  
		Size: 117.6 KB (117585 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:56bf9a0df8190cfee79e7aeeda0631ec01c1e03add7764e72439b78bf8a83c9d`  
		Last Modified: Sat, 05 May 2018 23:35:21 GMT  
		Size: 1.5 KB (1462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c876169315ef51cee45be25e01c775d725a7aaa68b93e8535f3b7ca46e5f773`  
		Last Modified: Tue, 08 May 2018 08:40:08 GMT  
		Size: 503.0 KB (502981 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:03d7fcd42a36df04a16d4e04fd2507eaf5d28179b0a40b73985bad5e375dfb77`  
		Last Modified: Tue, 08 May 2018 08:40:08 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `adminer:4-standalone` - linux; 386

```console
$ docker pull adminer@sha256:81ab268f58b711b5739ebd46f7faba2e0474fc1fcc7d3a3ef5b1ea7c8e149594
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **31.0 MB (30973544 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:689ebc485541714a28ec5eeebcdad89f0c08f7e77997e0c6feaecc1be94feeeb`
-	Entrypoint: `["entrypoint.sh","docker-php-entrypoint"]`
-	Default Command: `["php","-S","[::]:8080","-t","\/var\/www\/html"]`

```dockerfile
# Wed, 25 Oct 2017 23:32:08 GMT
ADD file:4a952fc4b81d50b342e26a818dac48a148a4d5eddb878219650e579a5c9faeaa in / 
# Wed, 25 Oct 2017 23:32:08 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 25 Oct 2017 23:32:08 GMT
CMD ["/bin/sh"]
# Tue, 24 Apr 2018 12:14:38 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Tue, 24 Apr 2018 12:14:43 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Tue, 24 Apr 2018 12:14:44 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Tue, 24 Apr 2018 12:14:44 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Tue, 24 Apr 2018 12:14:45 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Tue, 24 Apr 2018 12:14:45 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 24 Apr 2018 12:14:45 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Tue, 24 Apr 2018 12:14:45 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Tue, 24 Apr 2018 12:14:46 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Fri, 27 Apr 2018 12:25:46 GMT
ENV PHP_VERSION=7.2.5
# Fri, 27 Apr 2018 12:25:46 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.5.tar.xz.asc/from/this/mirror
# Fri, 27 Apr 2018 12:25:46 GMT
ENV PHP_SHA256=af70a33b3f7a51510467199b39af151333fbbe4cc21923bad9c7cf64268cddb2 PHP_MD5=
# Fri, 27 Apr 2018 12:25:54 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Fri, 27 Apr 2018 12:25:54 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Sat, 05 May 2018 14:33:52 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--enable-option-checking=fatal 				--disable-cgi 				--with-mhash 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Sat, 05 May 2018 14:33:53 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Sat, 05 May 2018 14:33:54 GMT
RUN docker-php-ext-enable sodium
# Sat, 05 May 2018 14:33:54 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Sat, 05 May 2018 14:33:54 GMT
CMD ["php" "-a"]
# Sat, 05 May 2018 20:17:42 GMT
STOPSIGNAL [SIGINT]
# Sat, 05 May 2018 20:17:43 GMT
RUN addgroup -S adminer &&	adduser -S -G adminer adminer &&	mkdir -p /var/www/html &&	mkdir -p /var/www/html/plugins-enabled &&	chown -R adminer:adminer /var/www/html
# Sat, 05 May 2018 20:17:43 GMT
WORKDIR /var/www/html
# Sat, 05 May 2018 20:17:44 GMT
RUN apk add --no-cache libpq
# Sat, 05 May 2018 20:18:04 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 	postgresql-dev 	sqlite-dev &&	docker-php-ext-install pdo_mysql pdo_pgsql pdo_sqlite &&	apk del .build-deps
# Sat, 05 May 2018 20:18:04 GMT
COPY multi:fcdffffd48fc0fc7ad3b317e64231ca1b160ab11eac6289d64ba2a4bdfd85ccc in /var/www/html/ 
# Sat, 05 May 2018 20:18:04 GMT
ENV ADMINER_VERSION=4.6.2
# Tue, 08 May 2018 10:38:52 GMT
ENV ADMINER_DOWNLOAD_SHA256=2b3e5e87ed1214288378fc272c1ba0497ec2f1128444e3a581eabd435f5575b9
# Tue, 08 May 2018 10:38:53 GMT
ENV ADMINER_SRC_DOWNLOAD_SHA256=13f26a5aeed2f734d9309a922592f2e2b35ba2ea5c1c2a2c8402ca26a8808682
# Tue, 08 May 2018 10:38:56 GMT
RUN set -x &&	curl -fsSL https://github.com/vrana/adminer/releases/download/v$ADMINER_VERSION/adminer-$ADMINER_VERSION.php -o adminer.php &&	echo "$ADMINER_DOWNLOAD_SHA256  adminer.php" |sha256sum -c - &&	curl -fsSL https://github.com/vrana/adminer/archive/v$ADMINER_VERSION.tar.gz -o source.tar.gz &&	echo "$ADMINER_SRC_DOWNLOAD_SHA256  source.tar.gz" |sha256sum -c - &&	tar xzf source.tar.gz --strip-components=1 "adminer-$ADMINER_VERSION/designs/" "adminer-$ADMINER_VERSION/plugins/" &&	rm source.tar.gz
# Tue, 08 May 2018 10:38:56 GMT
COPY file:7d0b9a0787be28f6522891c0b9e7249e1c7d88759916642b95d9d3296ed72be5 in /usr/local/bin/ 
# Tue, 08 May 2018 10:38:56 GMT
ENTRYPOINT ["entrypoint.sh" "docker-php-entrypoint"]
# Tue, 08 May 2018 10:38:56 GMT
USER [adminer]
# Tue, 08 May 2018 10:38:57 GMT
CMD ["php" "-S" "[::]:8080" "-t" "/var/www/html"]
# Tue, 08 May 2018 10:38:57 GMT
EXPOSE 8080/tcp
```

-	Layers:
	-	`sha256:ffe4428ef008913a7ec63449e4ad3aa536b26103943146a302591dfceb157d2f`  
		Last Modified: Sat, 17 Jun 2017 18:08:13 GMT  
		Size: 2.0 MB (2045593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f4fe786260f2bd2710289e7c9487b423cb252a691fa501759b0768516122869`  
		Last Modified: Wed, 25 Oct 2017 23:32:27 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63809d489c43deed491e4ee6f6197a80f95b5bb2432c1541adf8067a0af9eea6`  
		Last Modified: Tue, 24 Apr 2018 13:37:39 GMT  
		Size: 1.5 MB (1491632 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd9e9f882046d84bd48d78e57c220a56b21cf68c7e83784b84aa730aadecdb36`  
		Last Modified: Tue, 24 Apr 2018 13:37:38 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0afb730bcdd5e164ea8e691034340e56eb5bd44f77b405856325b77d6e084907`  
		Last Modified: Tue, 24 Apr 2018 13:37:38 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22857f0ffd40fd5f0e01c503a69f30d873876d2dc6a6ad8882a047d5aa8789d5`  
		Last Modified: Fri, 27 Apr 2018 13:09:09 GMT  
		Size: 12.1 MB (12054601 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f7993cbe3d4aa2c6758ed16f7c30d49838ee10215a5d81d1213385c0a410ae6`  
		Last Modified: Fri, 27 Apr 2018 13:09:07 GMT  
		Size: 498.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90a49f0de6fcac20f9291915f9ffc2f8aa035c151aa91b0f5f5f4bc43d356a16`  
		Last Modified: Sat, 05 May 2018 15:48:44 GMT  
		Size: 13.3 MB (13346627 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12eedaaae1044576af1c8ffe502fed02ea99eb0f070c48499efd2e42fd9bdf80`  
		Last Modified: Sat, 05 May 2018 15:48:39 GMT  
		Size: 2.2 KB (2168 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4ad05352f9c62baf01b4d442d7df8a56772646b6cddf2f0845f49ca1091f64b0`  
		Last Modified: Sat, 05 May 2018 15:48:39 GMT  
		Size: 70.3 KB (70288 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbb954381829f0dbeeacc36f4a4298c9fb326d9bf7f67724b6e485ff7793acb1`  
		Last Modified: Sat, 05 May 2018 20:18:50 GMT  
		Size: 1.4 KB (1360 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00e3bbd790be95014ffba468e0f81dcf86033cd5d16572bbe9bff61cad7158a8`  
		Last Modified: Sat, 05 May 2018 20:18:51 GMT  
		Size: 1.3 MB (1329865 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b4a42fa2708670b19e988bbf15701335f2f031d50a9105e0539285b15975a6d`  
		Last Modified: Sat, 05 May 2018 20:18:50 GMT  
		Size: 124.4 KB (124379 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dd56d58191689a28df36eb209aeebe8f2aa800330bbed9ae997a4947c7bb9d75`  
		Last Modified: Sat, 05 May 2018 20:18:50 GMT  
		Size: 1.5 KB (1462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07d658fbe1b71fb93dbd28d7003ae532d8d0b640bc15ddd9034d50ef4d44bbb3`  
		Last Modified: Tue, 08 May 2018 10:39:16 GMT  
		Size: 503.0 KB (502979 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6d226dd86a4620406296d9fdc1daa3e94f47191b86eb893c8b8ca6c2f1d8c7d`  
		Last Modified: Tue, 08 May 2018 10:39:15 GMT  
		Size: 499.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `adminer:4-standalone` - linux; ppc64le

```console
$ docker pull adminer@sha256:9ac995140ae72222650d499e31fed70edb827cbd664f65f873b64b4f14ad2746
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **30.1 MB (30112891 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:744e864274eb087bdabc80fdfa74e0d77ab34b0785c3aaa3a5cc9b41157b22b3`
-	Entrypoint: `["entrypoint.sh","docker-php-entrypoint"]`
-	Default Command: `["php","-S","[::]:8080","-t","\/var\/www\/html"]`

```dockerfile
# Wed, 25 Oct 2017 23:28:47 GMT
ADD file:e0be8616517d68cb80a2f9b74eb967cda22b9937bbcbe8b75b6153815a6f7761 in / 
# Wed, 25 Oct 2017 23:28:48 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Wed, 25 Oct 2017 23:28:50 GMT
CMD ["/bin/sh"]
# Fri, 01 Dec 2017 10:14:12 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c
# Fri, 01 Dec 2017 10:14:20 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz 		libressl
# Fri, 01 Dec 2017 10:14:24 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Fri, 01 Dec 2017 10:14:25 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Fri, 01 Dec 2017 10:14:28 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Fri, 01 Dec 2017 10:14:29 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 10:14:29 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Fri, 01 Dec 2017 10:14:31 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Fri, 01 Dec 2017 10:14:32 GMT
ENV GPG_KEYS=1729F83938DA44E27BA0F4D3DBDB397470D12172 B1B44D8F021E4E2D6021E995DC9FF8D3EE5AF27F
# Fri, 27 Apr 2018 09:18:37 GMT
ENV PHP_VERSION=7.2.5
# Fri, 27 Apr 2018 09:18:38 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.2.5.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.2.5.tar.xz.asc/from/this/mirror
# Fri, 27 Apr 2018 09:18:38 GMT
ENV PHP_SHA256=af70a33b3f7a51510467199b39af151333fbbe4cc21923bad9c7cf64268cddb2 PHP_MD5=
# Fri, 27 Apr 2018 09:18:47 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Fri, 27 Apr 2018 09:18:48 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Fri, 27 Apr 2018 09:22:33 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libressl-dev 		libsodium-dev 		libxml2-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 		--with-sodium=shared 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Fri, 27 Apr 2018 09:22:35 GMT
COPY multi:2cdcedabcf5a3b9ae610fab7848e94bc2f64b4d85710d55fd6f79e44dacf73d8 in /usr/local/bin/ 
# Fri, 27 Apr 2018 09:22:37 GMT
RUN docker-php-ext-enable sodium
# Fri, 27 Apr 2018 09:22:40 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Fri, 27 Apr 2018 09:22:40 GMT
CMD ["php" "-a"]
# Fri, 27 Apr 2018 10:27:38 GMT
STOPSIGNAL [SIGINT]
# Fri, 27 Apr 2018 10:27:40 GMT
RUN addgroup -S adminer &&	adduser -S -G adminer adminer &&	mkdir -p /var/www/html &&	mkdir -p /var/www/html/plugins-enabled &&	chown -R adminer:adminer /var/www/html
# Fri, 27 Apr 2018 10:27:40 GMT
WORKDIR /var/www/html
# Fri, 27 Apr 2018 10:27:43 GMT
RUN apk add --no-cache libpq
# Fri, 27 Apr 2018 10:28:19 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 	postgresql-dev 	sqlite-dev &&	docker-php-ext-install pdo_mysql pdo_pgsql pdo_sqlite &&	apk del .build-deps
# Fri, 27 Apr 2018 10:28:20 GMT
COPY multi:fcdffffd48fc0fc7ad3b317e64231ca1b160ab11eac6289d64ba2a4bdfd85ccc in /var/www/html/ 
# Fri, 27 Apr 2018 10:28:21 GMT
ENV ADMINER_VERSION=4.6.2
# Fri, 27 Apr 2018 10:28:22 GMT
ENV ADMINER_DOWNLOAD_SHA256=4b8e0d184a1f0c5ec2c077fd20a06d3e27877d8a63fd4f75aaf92abb103ff458
# Fri, 27 Apr 2018 10:28:23 GMT
ENV ADMINER_SRC_DOWNLOAD_SHA256=13f26a5aeed2f734d9309a922592f2e2b35ba2ea5c1c2a2c8402ca26a8808682
# Fri, 27 Apr 2018 10:28:36 GMT
RUN set -x &&	curl -fsSL https://github.com/vrana/adminer/releases/download/v$ADMINER_VERSION/adminer-$ADMINER_VERSION-en.php -o adminer.php &&	echo "$ADMINER_DOWNLOAD_SHA256  adminer.php" |sha256sum -c - &&	curl -fsSL https://github.com/vrana/adminer/archive/v$ADMINER_VERSION.tar.gz -o source.tar.gz &&	echo "$ADMINER_SRC_DOWNLOAD_SHA256  source.tar.gz" |sha256sum -c - &&	tar xzf source.tar.gz --strip-components=1 "adminer-$ADMINER_VERSION/designs/" "adminer-$ADMINER_VERSION/plugins/" &&	rm source.tar.gz
# Fri, 27 Apr 2018 10:28:40 GMT
COPY file:7d0b9a0787be28f6522891c0b9e7249e1c7d88759916642b95d9d3296ed72be5 in /usr/local/bin/ 
# Fri, 27 Apr 2018 10:28:40 GMT
ENTRYPOINT ["entrypoint.sh" "docker-php-entrypoint"]
# Fri, 27 Apr 2018 10:28:41 GMT
USER [adminer]
# Fri, 27 Apr 2018 10:28:42 GMT
CMD ["php" "-S" "[::]:8080" "-t" "/var/www/html"]
# Fri, 27 Apr 2018 10:28:44 GMT
EXPOSE 8080/tcp
```

-	Layers:
	-	`sha256:1e52418956f7d2a8ea35e8e6e3318fd08e005b27457d77868c225e7433bbfa02`  
		Last Modified: Thu, 20 Jul 2017 15:12:59 GMT  
		Size: 2.0 MB (2008578 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:acf472f4e5bb7956ac20bb343b304e1d3de1f79160c0d158cccbe25980022d50`  
		Last Modified: Wed, 25 Oct 2017 23:29:11 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f84cc6cff0254c78cff642b43cf3648847bcab3fff737bcbe0b27f56cfb6ee6`  
		Last Modified: Fri, 01 Dec 2017 11:26:19 GMT  
		Size: 1.4 MB (1379960 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:632c20d36eba51c8e0a05660044d86653e4b3b3437a3a66004f52d460a238fa1`  
		Last Modified: Fri, 01 Dec 2017 11:26:19 GMT  
		Size: 1.3 KB (1277 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7780319f82f8282646bd74934ca8189f7db220ff03d2f5e67b9386493464d698`  
		Last Modified: Fri, 01 Dec 2017 11:26:18 GMT  
		Size: 199.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2256e0d7b9db6d77b58a655fe08cdb2e72dbae4aefcc584057bfb857e8492904`  
		Last Modified: Fri, 27 Apr 2018 10:06:03 GMT  
		Size: 12.1 MB (12054639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5492be5a418c21ec374ede995e9dcc6fdf89ecd6eaa1ed558f99e687a5483ece`  
		Last Modified: Fri, 27 Apr 2018 10:06:02 GMT  
		Size: 497.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f825dcd1ffbdedba45faee7e501afec3b5bc2b3610ec30d019eb6803be842bf`  
		Last Modified: Fri, 27 Apr 2018 10:06:06 GMT  
		Size: 12.9 MB (12903749 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e60c0a2ab03c9ac764da433b26fae8d7f2afeaca603f6a43071ed6fba142acfc`  
		Last Modified: Fri, 27 Apr 2018 10:06:02 GMT  
		Size: 2.2 KB (2169 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e2ecc941f876bec64cb689d52b0ffa263edca83369056bfc023c2b4d53378f5`  
		Last Modified: Fri, 27 Apr 2018 10:06:02 GMT  
		Size: 71.1 KB (71100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b88ec5267f6be2df71a42b84087ce3909f9ff5f3bff4a37e247364b4b7041ad`  
		Last Modified: Fri, 27 Apr 2018 10:30:00 GMT  
		Size: 1.4 KB (1408 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6488a918ead962bb10ff5c0e15bf30b529a8ffd9db520017f16614081b74602`  
		Last Modified: Fri, 27 Apr 2018 10:29:57 GMT  
		Size: 1.2 MB (1202127 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1d94d8fe0cb38403d29756cb87248ecdee620ae402ca9282fd17cbe87990d4d`  
		Last Modified: Fri, 27 Apr 2018 10:29:56 GMT  
		Size: 124.9 KB (124939 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:737195b6684923286c559c8079899874210549da876178776f67ec8f075896b2`  
		Last Modified: Fri, 27 Apr 2018 10:29:57 GMT  
		Size: 1.5 KB (1463 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b91957ff604bb665cf2bf59f62efc659790a2224934aa0c73ad0f7d5844c452d`  
		Last Modified: Fri, 27 Apr 2018 10:29:57 GMT  
		Size: 360.1 KB (360115 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd8640f0eed812929315c4f03b94a31e22914cfd376290594aafe895506d1b0`  
		Last Modified: Fri, 27 Apr 2018 10:29:56 GMT  
		Size: 495.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
