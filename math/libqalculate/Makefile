PORTNAME=	libqalculate
PORTVERSION=	5.4.0
PORTREVISION=	1
CATEGORIES=	math
MASTER_SITES=	https://github.com/Qalculate/${PORTNAME}/releases/download/v${PORTVERSION}/

PATCH_SITES=	https://github.com/Qalculate/libqalculate/commit/
PATCHFILES+=	0d81784d2c85ca90b5a660b70862b9572be661e3.patch:-p1 # https://github.com/Qalculate/libqalculate/issues/722

MAINTAINER=	jhale@FreeBSD.org
COMMENT=	Multi-purpose desktop calculator (backend library)
WWW=		https://qalculate.github.io/

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libicuuc.so:devel/icu \
		libcurl.so:ftp/curl \
		libgmp.so:math/gmp \
		libmpfr.so:math/mpfr

USES=		compiler:c++14-lang gettext gmake gnome iconv libtool \
		localbase ncurses pathfix pkgconfig readline
USE_GNOME=	intltool libxml2
USE_LDCONFIG=	yes

GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip

OPTIONS_DEFINE=	NLS
OPTIONS_SUB=	yes

post-patch-NLS-off:
	@${REINPLACE_CMD} -e '/^SUBDIRS =/s|po ||g' ${WRKSRC}/Makefile.in

post-patch:
	@${REINPLACE_CMD} -e '/^SUBDIRS =/s|docs||g' ${WRKSRC}/Makefile.in

.include <bsd.port.mk>
