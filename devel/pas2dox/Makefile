PORTNAME=	pas2dox
DISTVERSION=	0.50rc1
CATEGORIES=	devel converters
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}/${PORTNAME}-${DISTVERSION}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Preprocessor to use doxygen with Pascal sources
WWW=		https://pas2dox.sourceforge.net

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

BROKEN=			compilation fails: no matching function for call to 'transform'
DEPRECATED=		doesn't compile with moddern clang and gcc, upstream last updated it in 2003
EXPIRATION_DATE=	2025-01-15

WRKSRC=		${WRKDIR}/${PORTNAME}

USES=		gmake
ALL_TARGET=	${PORTNAME}

PLIST_FILES=	bin/${PORTNAME}

post-patch:
	@${REINPLACE_CMD} -e \
		's|^LEX=|LEX?=| ; \
		 s|$${CC} $$<|$${CXX} $${CXXFLAGS} $$<|' ${WRKSRC}/Makefile
	@${REINPLACE_CMD} -e \
		's|yy_flex_realloc|yyrealloc|' ${WRKSRC}/${PORTNAME}.l

pre-build:
	@${RM} ${WRKSRC}/${PORTNAME}.cpp

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>
