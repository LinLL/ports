# $FreeBSD$

PORTNAME=	qdbusviewer
DISTVERSION=	${QT5_VERSION}
PORTREVISION=	1
CATEGORIES=	devel
PKGNAMEPREFIX=	qt5-

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Qt 5 graphical interface to D-Bus

USE_QT5=	core dbus widgets xml buildtools_build
QT_DIST=	tools
USES=		qmake

DESKTOP_ENTRIES="Qt 5 D-Bus Viewer" "" \
		"${PREFIX}/share/pixmaps/qdbusviewer-qt5.png" \
		"${PREFIX}/${QT_BINDIR_REL}/qdbusviewer" \
		"Development;Qt;" true

WRKSRC_SUBDIR=	src/qdbus/${PORTNAME}

post-install:
	${INSTALL_DATA} ${WRKSRC}/images/qdbusviewer-128.png \
		${STAGEDIR}${PREFIX}/share/pixmaps/qdbusviewer-qt5.png

.include <bsd.port.mk>
