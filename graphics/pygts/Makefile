# Created by: Wen Heping <wenheping@gmail.com>
# $FreeBSD$

PORTNAME=	pygts
PORTVERSION=	0.3.1
PORTREVISION=	4
CATEGORIES=	graphics python
MASTER_SITES=	SF

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Python binding for GNU Triangulated Surface(GTS) Library

BUILD_DEPENDS=	${PYNUMPY}
RUN_DEPENDS=	${PYNUMPY}
LIB_DEPENDS=	libgts.so:${PORTSDIR}/graphics/gts

USE_PYTHON=	distutils
USES=		pkgconfig python

.include <bsd.port.mk>
