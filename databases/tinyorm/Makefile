PORTNAME=	tinyorm
DISTVERSION=	v0.38.1
CATEGORIES=	databases
PKGNAMEPREFIX=	qt6-

MAINTAINER=	alonsoschaich@fastmail.fm
COMMENT=	Qt based Object Relation Manager
WWW=		https://www.tinyorm.org/

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		cmake:testing compiler:c++20-lang qt:6
USE_QT=		base

MY_DEPENDS=	range-v3>0:devel/range-v3 \
		tabulate>0:devel/tabulate
BUILD_DEPENDS=	${MY_DEPENDS}
RUN_DEPENDS=	${MY_DEPENDS}
TEST_DEPENDS=	qt6-base_sqldriver-sqlite>0:databases/qt6-base_sqldriver

CMAKE_ARGS=	-DTINY_PORT:STRING=${PORTNAME}
CMAKE_OFF=	CMAKE_CXX_SCAN_FOR_MODULES \
		CMAKE_EXPORT_PACKAGE_REGISTRY \
		BUILD_TREE_DEPLOY
CMAKE_TESTING_ON=	BUILD_TESTS
CMAKE_TESTING_SETENV=	yes
TEST_ENV=	DB_SQLITE_DATABASE=${TEST_WRKSRC}/test.sqlite \
		DB_AUTOMIGRATE=ON

USE_GITHUB=	yes
GH_ACCOUNT=	silverqx
GH_PROJECT=	TinyORM

.include <bsd.port.mk>
