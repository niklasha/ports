PHP_VERSION=	8.4.27
REVISION=	0

AUTOCONF_VERSION= 2.73

PHP_PKGSPEC=	>=8.4,<8.5
ZEND_EXTENSIONS= -opcache
CONFIGURE_ARGS=	--enable-opcache \
		--with-pic

WANTLIB-pdo_odbc += iodbcinst

.include <bsd.port.mk>
