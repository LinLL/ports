# $FreeBSD$

PORTNAME=	libcdr
PORTVERSION=	0.1.0
PORTREVISION=	1
CATEGORIES=	graphics devel
MASTER_SITES=	LODEV
PKGNAMESUFFIX=	01

MAINTAINER=	office@FreeBSD.org
COMMENT=	Library and tools for parsing Corel Draw file format

LICENSE=	LGPL21 MPL GPLv2
LICENSE_COMB=	dual

BUILD_DEPENDS=	${LOCALBASE}/include/boost/optional.hpp:${PORTSDIR}/devel/boost-libs
LIB_DEPENDS=	libicui18n.so:${PORTSDIR}/devel/icu \
		librevenge-0.0.so:${PORTSDIR}/textproc/librevenge \
		liblcms2.so:${PORTSDIR}/graphics/lcms2

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--disable-werror --without-docs
USES=	libtool pathfix pkgconfig tar:xz
USE_LDCONFIG=	yes
INSTALL_TARGET=	install-strip

CPPFLAGS+=	-I${LOCALBASE}/include
CXXFLAGS+=	-Wno-long-long

post-patch:
	@${REINPLACE_CMD} -e "s,zlib,,g" ${WRKSRC}/libcdr.pc.in

.include <bsd.port.mk>
