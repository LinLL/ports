# Created by: Johannes Meixner <xmj@chaot.net>
# $FreeBSD$

PORTNAME=	pulseaudio-libs
PORTVERSION=	0.9.21
PORTREVISION=	1
CATEGORIES=	audio linux

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	Libraries for PulseAudio clients (Linux CentOS ${LINUX_DIST_VER})

USE_LINUX=	c6
USE_LINUX_RPM=	yes
USE_LINUX_APPS=	dbuslibs libasyncns libsndfile xorglibs

RPMVERSION=	14.el6_3
USE_LDCONFIG=	yes

DOCSDIR=	${PREFIX}/usr/share/doc/pulseaudio-${PORTVERSION}
DESCR=		${.CURDIR}/../pulseaudio/pkg-descr
SRC_DISTFILES=	pulseaudio-${PORTVERSION}-${RPMVERSION}${SRC_SUFX}

post-extract:
	@${RM} -r ${WRKSRC}/usr/bin ${WRKSRC}/etc/rc.d ${WRKSRC}/etc/sysconfig

.include <bsd.port.mk>
