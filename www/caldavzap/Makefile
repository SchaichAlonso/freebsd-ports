PORTNAME=	caldavzap
PORTVERSION=	0.13.1
PORTREVISION=	2
CATEGORIES=	www
MASTER_SITES=	https://www.inf-it.com/
DISTNAME=	CalDavZAP_${PORTVERSION}

MAINTAINER=	gahr@FreeBSD.org
COMMENT=	CalDAV web client implementation
WWW=		https://www.inf-it.com/open-source/clients/caldavzap/

LICENSE=	AGPLv3

WRKSRC=		${WRKDIR}/${PORTNAME}
USES=		php zip
NO_BUILD=	yes

do-install:
	${MKDIR} ${STAGEDIR}${WWWDIR}
	${MV} ${WRKSRC}/config.js ${WRKSRC}/config.js.sample
	cd ${WRKSRC} && ${COPYTREE_SHARE} . ${STAGEDIR}${WWWDIR}

.include <bsd.port.mk>
