## `nextcloud:12-rc-apache`

```console
$ docker pull nextcloud@sha256:6b94fde238afb89a193c978db6927eee98357fa7215172358f239db72b16a500
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `nextcloud:12-rc-apache` - linux; amd64

```console
$ docker pull nextcloud@sha256:8b2e0cc12ab139456ffe19cc9ef1853f8be649c590691d13b9e0944c8898b24c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **229.9 MB (229881294 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:680534a977cc18df0fbd82e7fd206eb94481545da9db70f792bf3652277810bf`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 13 Mar 2018 21:57:21 GMT
ADD file:bc844c4763367b5f0ac7b9aebf7d43900d98f2aca101b886f185347b24973dbe in / 
# Tue, 13 Mar 2018 21:57:22 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 14:55:44 GMT
RUN set -eux; 	{ 		echo 'Package: php*'; 		echo 'Pin: release *'; 		echo 'Pin-Priority: -1'; 	} > /etc/apt/preferences.d/no-debian-php
# Wed, 14 Mar 2018 14:55:44 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		make 		pkg-config 		re2c
# Wed, 14 Mar 2018 14:56:24 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Wed, 14 Mar 2018 14:56:24 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Wed, 14 Mar 2018 14:56:25 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Wed, 14 Mar 2018 15:16:42 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 15:16:42 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Wed, 14 Mar 2018 15:16:42 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Wed, 14 Mar 2018 15:16:43 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Wed, 14 Mar 2018 15:16:44 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Wed, 14 Mar 2018 15:16:45 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Wed, 14 Mar 2018 15:16:45 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Wed, 14 Mar 2018 15:16:45 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Wed, 14 Mar 2018 15:16:46 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Wed, 14 Mar 2018 15:16:46 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 14 Mar 2018 15:16:46 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 14 Mar 2018 15:16:46 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Wed, 14 Mar 2018 15:16:47 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172
# Thu, 05 Apr 2018 03:27:47 GMT
ENV PHP_VERSION=7.1.16
# Thu, 05 Apr 2018 03:27:47 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.16.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.16.tar.xz.asc/from/this/mirror
# Thu, 05 Apr 2018 03:27:47 GMT
ENV PHP_SHA256=a5d67e477248a3911af7ef85c8400c1ba8cd632184186fd31070b96714e669f1 PHP_MD5=
# Thu, 05 Apr 2018 03:28:15 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	if ! command -v gpg > /dev/null; then 		fetchDeps="$fetchDeps 			dirmngr 			gnupg 		"; 	fi; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -rf "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $fetchDeps
# Thu, 05 Apr 2018 03:28:15 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Thu, 05 Apr 2018 03:31:07 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 		zlib1g-dev 		${PHP_EXTRA_BUILD_DEPS:-} 	; 	rm -rf /var/lib/apt/lists/*; 		export 		CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	; 	docker-php-source extract; 	cd /usr/src/php; 	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 	debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)"; 	if [ ! -d /usr/include/curl ]; then 		ln -sT "/usr/include/$debMultiarch/curl" /usr/local/include/curl; 	fi; 	./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				$(test "$gnuArch" = 's390x-linux-gnu' && echo '--without-pcre-jit') 		--with-libdir="lib/$debMultiarch" 				${PHP_EXTRA_CONFIGURE_ARGS:-} 	; 	make -j "$(nproc)"; 	make install; 	find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; 	make clean; 	cd /; 	docker-php-source delete; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 		php --version; 		pecl update-channels; 	rm -rf /tmp/pear ~/.pearrc
# Thu, 05 Apr 2018 03:31:08 GMT
COPY multi:cb6c9a453a971f0ed6bdf30b12bc250bbe068005b3c3b084f5048cbf9787fb8d in /usr/local/bin/ 
# Thu, 05 Apr 2018 03:31:08 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Thu, 05 Apr 2018 03:31:09 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Thu, 05 Apr 2018 03:31:09 GMT
WORKDIR /var/www/html
# Thu, 05 Apr 2018 03:31:09 GMT
EXPOSE 80/tcp
# Thu, 05 Apr 2018 03:31:10 GMT
CMD ["apache2-foreground"]
# Thu, 05 Apr 2018 13:08:22 GMT
RUN set -ex;         apt-get update;     apt-get install -y --no-install-recommends         rsync         bzip2         busybox-static     ;     rm -rf /var/lib/apt/lists/*;         mkdir -p /var/spool/cron/crontabs;     echo '*/15 * * * * php -f /var/www/html/cron.php' > /var/spool/cron/crontabs/www-data
# Thu, 05 Apr 2018 13:11:42 GMT
RUN set -ex;         savedAptMark="$(apt-mark showmanual)";         apt-get update;     apt-get install -y --no-install-recommends         libcurl4-openssl-dev         libfreetype6-dev         libicu-dev         libjpeg-dev         libldap2-dev         libmcrypt-dev         libmemcached-dev         libpng12-dev         libpq-dev         libxml2-dev     ;         debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)";     docker-php-ext-configure gd --with-freetype-dir=/usr --with-png-dir=/usr --with-jpeg-dir=/usr;     docker-php-ext-configure ldap --with-libdir="lib/$debMultiarch";     docker-php-ext-install         exif         gd         intl         ldap         mbstring         mcrypt         mysqli         opcache         pcntl         pdo_mysql         pdo_pgsql         pgsql         zip     ;     pecl install         APCu-5.1.11         memcached-3.0.4         redis-3.1.6     ;     docker-php-ext-enable         apcu         memcached         redis     ;         apt-mark auto '.*' > /dev/null;     apt-mark manual $savedAptMark;     ldd "$(php -r 'echo ini_get("extension_dir");')"/*.so         | awk '/=>/ { print $3 }'         | sort -u         | xargs -r dpkg-query -S         | cut -d: -f1         | sort -u         | xargs -rt apt-mark manual;         apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false;     rm -rf /var/lib/apt/lists/*
# Thu, 19 Apr 2018 16:20:06 GMT
RUN {         echo 'opcache.enable=1';         echo 'opcache.enable_cli=1';         echo 'opcache.interned_strings_buffer=8';         echo 'opcache.max_accelerated_files=10000';         echo 'opcache.memory_consumption=128';         echo 'opcache.save_comments=1';         echo 'opcache.revalidate_freq=1';     } > /usr/local/etc/php/conf.d/opcache-recommended.ini;         mkdir /var/www/data;     chown -R www-data:root /var/www;     chmod -R g=u /var/www
# Thu, 19 Apr 2018 16:20:07 GMT
VOLUME [/var/www/html]
# Thu, 19 Apr 2018 16:20:08 GMT
RUN a2enmod rewrite remoteip ;    {     echo RemoteIPHeader X-Real-IP ;     echo RemoteIPTrustedProxy 10.0.0.0/8 ;     echo RemoteIPTrustedProxy 172.16.0.0/12 ;     echo RemoteIPTrustedProxy 192.168.0.0/16 ;    } > /etc/apache2/conf-available/remoteip.conf;    a2enconf remoteip
# Thu, 19 Apr 2018 16:24:10 GMT
ENV NEXTCLOUD_VERSION=12.0.7RC1
# Thu, 19 Apr 2018 16:24:27 GMT
RUN set -ex;     curl -fsSL -o nextcloud.tar.bz2         "https://download.nextcloud.com/server/prereleases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2";     curl -fsSL -o nextcloud.tar.bz2.asc         "https://download.nextcloud.com/server/prereleases/nextcloud-${NEXTCLOUD_VERSION}.tar.bz2.asc";     export GNUPGHOME="$(mktemp -d)";     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 28806A878AE423A28372792ED75899B9A724937A;     gpg --batch --verify nextcloud.tar.bz2.asc nextcloud.tar.bz2;     rm -r "$GNUPGHOME" nextcloud.tar.bz2.asc;     tar -xjf nextcloud.tar.bz2 -C /usr/src/;     rm nextcloud.tar.bz2;     rm -rf /usr/src/nextcloud/updater;     mkdir -p /usr/src/nextcloud/data;     mkdir -p /usr/src/nextcloud/custom_apps;     chmod +x /usr/src/nextcloud/occ
# Thu, 19 Apr 2018 16:24:28 GMT
COPY multi:60e3cd03e05bfb8b6202821a8e0d4fcac7ec23796138bf6c73774235efb566e1 in / 
# Thu, 19 Apr 2018 16:24:29 GMT
COPY multi:a4ce16f733fa0a4cb4b62b3fe3229e71f5a6b970a03b912772780cdb452098f4 in /usr/src/nextcloud/config/ 
# Thu, 19 Apr 2018 16:24:29 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 19 Apr 2018 16:24:29 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:f2b6b4884fc8b2f1fcef843f92f7c82c9c149df85ac77e5f0de7a342ae442412`  
		Last Modified: Tue, 13 Mar 2018 22:43:41 GMT  
		Size: 52.6 MB (52608519 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8db887c458002053abb80fe7da3ed9071bad3ba45e982f07779927d7baf62bad`  
		Last Modified: Wed, 14 Mar 2018 16:28:53 GMT  
		Size: 229.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e0e41c52c70a0be891e3c033156b95b2b3183dadfd9f725f93f45e25e35bc73`  
		Last Modified: Wed, 14 Mar 2018 16:29:09 GMT  
		Size: 76.3 MB (76346297 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbc9ac078c49076a62b6a3c52b26b4af4537e8bb2b315f8c15d26061d58f99b4`  
		Last Modified: Wed, 14 Mar 2018 16:28:57 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4c6f6be74883f5e84dc330d067c90524b189a7b5259aa9666411eea6c6928cd`  
		Last Modified: Wed, 14 Mar 2018 16:32:36 GMT  
		Size: 4.5 MB (4466582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a28db8adaf05e1ae06e8838612042869200e3f983f9be2777cb1e10f24a33baf`  
		Last Modified: Wed, 14 Mar 2018 16:32:33 GMT  
		Size: 1.3 KB (1253 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61afa9c0aff1a84d4399f4ab1f210d5152d0f738b7637e820d31c7ab061b1a86`  
		Last Modified: Wed, 14 Mar 2018 16:32:32 GMT  
		Size: 427.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a30b1659c04663754eea845c8a9d9ab3fe69a9836cda20dce45d4297a8564b41`  
		Last Modified: Wed, 14 Mar 2018 16:32:31 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b04c4f5caef73449ee33b950e6a0d372bb117c197cec0a620cf5348c2cde0385`  
		Last Modified: Wed, 14 Mar 2018 16:32:31 GMT  
		Size: 484.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7278cc5a29f0bd362c22ffa4cab8bda888258be8d7859e5724f6a7a85bc115f5`  
		Last Modified: Thu, 05 Apr 2018 07:54:55 GMT  
		Size: 12.6 MB (12564292 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:147f057d2659b313a398cd74dad1d42a3b0550ecb8db309a301fb88b9784fde7`  
		Last Modified: Thu, 05 Apr 2018 07:54:54 GMT  
		Size: 502.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3cf22ca2bf74ed4b9fa4b394ef9970261b28efad861729ec7049fa012052075a`  
		Last Modified: Thu, 05 Apr 2018 07:54:58 GMT  
		Size: 16.0 MB (16037230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2414da87e5ca19b8022889e740c56f2895929fcad606ddbcc0204d5947f7cb7`  
		Last Modified: Thu, 05 Apr 2018 07:54:54 GMT  
		Size: 2.2 KB (2188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb11d4e98093211147a47ec649b51a3d1107d62b455c6c22e1fe8c4d8899a589`  
		Last Modified: Thu, 05 Apr 2018 07:54:54 GMT  
		Size: 903.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a87e2a6c61277031bbd1330d7ce0fb0522c6d03005eee89ce7cb9f29fa545b9a`  
		Last Modified: Thu, 05 Apr 2018 14:48:58 GMT  
		Size: 1.9 MB (1856995 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61352a54f9f5c44b957a06434124a90d245627225f191077bb877981938d9d8a`  
		Last Modified: Thu, 05 Apr 2018 14:49:02 GMT  
		Size: 16.5 MB (16491462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b84dd2c128fdcf0c69c9481efb2ea35eae53ce94fcb0510f586443b2db12351a`  
		Last Modified: Thu, 19 Apr 2018 17:38:30 GMT  
		Size: 432.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:693eaac5c685ad21526300650138be77221a2892864e35ff959aa9acc78b6fdf`  
		Last Modified: Thu, 19 Apr 2018 17:38:31 GMT  
		Size: 545.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0f7678bf742324c9dfa2417dddcdbddaba08d2f2ef7e89c7c8ea96bf4c44bb4`  
		Last Modified: Thu, 19 Apr 2018 18:17:37 GMT  
		Size: 49.5 MB (49500677 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eff6c6c2f40cba3ddc4e98f310ebd65da92f25f2f15ed87d4ff0d28ecb39d82d`  
		Last Modified: Thu, 19 Apr 2018 18:17:20 GMT  
		Size: 1.0 KB (1015 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9d81b949ffdd9f4024078b71605478e5f891573bb9a5ae8fbe86c864012cfe7`  
		Last Modified: Thu, 19 Apr 2018 18:17:20 GMT  
		Size: 849.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip