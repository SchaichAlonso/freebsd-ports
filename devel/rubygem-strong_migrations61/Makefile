PORTNAME=	strong_migrations
DISTVERSION=	2.0.0
CATEGORIES=	devel rubygems
MASTER_SITES=	RG
PKGNAMESUFFIX=	61

MAINTAINER=	bofh@FreeBSD.org
COMMENT=	Catch unsafe migrations at dev time
WWW=		https://github.com/ankane/strong_migrations

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

DEPRECATED=	Ruby on Rails 6.1.x reached EOL on 2024-10-01
EXPIRATION_DATE=2025-01-23

RUN_DEPENDS=	rubygem-activerecord61>=5.2:databases/rubygem-activerecord61

USES=		gem

NO_ARCH=	yes

.include <bsd.port.mk>
