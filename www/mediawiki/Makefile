# $OpenBSD: Makefile,v 1.44 2013/09/19 14:19:20 kirby Exp $

COMMENT =	web-based collaborative editing environment

V =		1.37.2
DISTNAME =	mediawiki-${V}
CATEGORIES =	www

HOMEPAGE =	http://www.mediawiki.org/

MAINTAINER =	Niklas Hallqvist <niklas@appli.se>

# GPLv2+
PERMIT_PACKAGE = Yes

MASTER_SITES=	http://download.wikimedia.org/mediawiki/${V:R}/

NO_BUILD=	Yes
NO_TEST=	Yes
PKG_ARCH=	*

PREFIX=		${VARBASE}/www
INSTDIR=	${PREFIX}/mediawiki
SUBST_VARS=	INSTDIR

MODULES=	lang/php
RUN_DEPENDS=	lang/php/${MODPHP_VERSION},-gd \
		php-mysqli-${MODPHP_VSPEC}|php-pgsql-${MODPHP_VSPEC}|php-sqlite3-${MODPHP_VSPEC}:lang/php/${MODPHP_VERSION},-mysqli

do-install:
	@${INSTALL_DATA_DIR} ${INSTDIR}
	@cd ${WRKSRC} && pax -rw * ${INSTDIR}
	@find ${INSTDIR} \( -name '.cvsignore' -or -name \*.orig \) -exec rm -f {} +
	@chown -R ${SHAREOWN}:${SHAREGRP} ${INSTDIR}

.include <bsd.port.mk>
