PORTNAME=	tdfsb
PORTVERSION=	0.0.10
PORTREVISION=	10
CATEGORIES=	x11-fm
MASTER_SITES=	http://www.determinate.net/webdata/data/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	3D filesystem browser
WWW=		https://www.determinate.net/webdata/seg/tdfsb.html

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

DEPRECATED=	Unmaintained, uses smpeg which has no distfiles anymore
EXPIRATION_DATE=2025-01-30

LIB_DEPENDS=	libsmpeg.so:multimedia/smpeg

USES=		gl pkgconfig sdl
USE_GL=		glut
USE_SDL=	image sdl

PORTDOCS=	README
PLIST_FILES=	bin/${PORTNAME}

CPPFLAGS+=	`${LOCALBASE}/bin/pkgconf --cflags SDL_image gl` \
		`${LOCALBASE}/bin/smpeg-config --cflags` \
		-I ${LOCALBASE}/include
LDFLAGS+=	`${LOCALBASE}/bin/pkgconf --libs SDL_image gl` \
		`${LOCALBASE}/bin/smpeg-config --libs` \
		-L ${LOCALBASE}/lib -lGLU -lglut -lm

OPTIONS_DEFINE=	DOCS

do-build:
	(cd ${BUILD_WRKSRC} && ${CC} ${CPPFLAGS} ${CFLAGS} ${PORTNAME}.c \
		-o ${PORTNAME} ${LDFLAGS})

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin

do-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
