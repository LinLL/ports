# Created by: Denis Barov
# $FreeBSD$

PORTNAME=	smbnetfs
PORTVERSION=	0.5.3b
CATEGORIES=	sysutils net
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}/SMBNetFS-${PORTVERSION}
PKGNAMEPREFIX=	fusefs-

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Mount smb shares (Fuse filesystem)

LICENSE=	GPLv2

LIB_DEPENDS=	libsmbclient.so:${PORTSDIR}/net/samba-libsmbclient

OPTIONS_DEFINE=	DOCS GNOME_KEYRING
OPTIONS_DEFAULT=GNOME_KEYRING

GNOME_KEYRING_DESC=		Build with gnome-keyring support
GNOME_KEYRING_CONFIGURE_WITH=	gnome-keyring
GNOME_KEYRING_LIB_DEPENDS=	libgnome-keyring.so:${PORTSDIR}/security/libgnome-keyring

DOCSDIR=	${PREFIX}/share/doc/${PORTNAME}-${PORTVERSION}

USES=		fuse iconv pkgconfig tar:bzip2

GNU_CONFIGURE=	yes
CFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib
SUB_FILES=	pkg-message

.include <bsd.port.mk>
