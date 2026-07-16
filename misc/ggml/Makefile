PORTNAME=	ggml
DISTVERSIONPREFIX=	v
DISTVERSION=	0.13.1
CATEGORIES=	misc # machine-learning

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Tensor library for machine learning
WWW=		https://github.com/ggml-org/ggml

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

BROKEN_i386=	compilation fails: LLVM ERROR: out of memory

BUILD_DEPENDS=	spirv-headers>0:graphics/spirv-headers

USES=		cmake:testing compiler:c++17-lang llvm:build,min=22 python:run shebangfix
USE_LDCONFIG=	yes

USE_GITHUB=	yes
GH_ACCOUNT=	ggml-org

CMAKE_ON=	BUILD_SHARED_LIBS \
		GGML_BACKEND_DL \
		GGML_CPU_ALL_VARIANTS
CMAKE_OFF=	GGML_NATIVE \
		GGML_BUILD_TESTS \
		GGML_BUILD_EXAMPLES
CMAKE_TESTING_ON=	GGML_BUILD_TESTS

CMAKE_ARGS+=	-DGGML_BACKEND_DIR=${PREFIX}/lib

BINARY_ALIAS=	git=false

PLIST_SUB+=	DISTVERSION=${DISTVERSION}

OPTIONS_DEFINE=		VULKAN
OPTIONS_DEFAULT=	VULKAN
OPTIONS_SUB=		yes

VULKAN_CMAKE_BOOL=	GGML_VULKAN
VULKAN_BUILD_DEPENDS=	glslc:graphics/shaderc \
			vulkan-headers>0:graphics/vulkan-headers
VULKAN_LIB_DEPENDS=	libvulkan.so:graphics/vulkan-loader

# tests as of 0.13.1: 100% tests passed, 0 tests failed out of 21

.include <bsd.port.mk>
