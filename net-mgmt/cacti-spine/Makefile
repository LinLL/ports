# Created by: clement@FreeBSD.org
# $FreeBSD$

PORTNAME=	spine
PORTVERSION=	0.8.8b
PORTREVISION=	1
CATEGORIES=	net-mgmt
MASTER_SITES=	http://www.cacti.net/downloads/${PORTNAME}/
DISTNAME=	cacti-${PORTNAME}-${PORTVERSION}

MAINTAINER=	skreuzer@FreeBSD.org
COMMENT=	Multithreaded poller for Cacti written in C

LICENSE=	GPLv2

LIB_DEPENDS=	libnetsnmp.so:${PORTSDIR}/net-mgmt/net-snmp

GNU_CONFIGURE=	YES
CONFIGURE_ARGS+=--with-mysql=${LOCALBASE} --with-snmp=${LOCALBASE}
CPPFLAGS+=	`net-snmp-config --cflags`
LIBS+=		`net-snmp-config --libs`
USES=		libtool
USE_MYSQL=	YES
USE_OPENSSL=	YES

post-patch:
	@${REINPLACE_CMD} 's,#define\ *DEFAULT_CONF_FILE .*,#define DEFAULT_CONF_FILE "${PREFIX}/etc/spine.conf",' ${WRKSRC}/spine.h

post-install:
	${MV} ${STAGEDIR}${PREFIX}/etc/spine.conf.dist ${STAGEDIR}${PREFIX}/etc/spine.conf.sample

.include <bsd.port.mk>
