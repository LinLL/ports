# Created by: Steve Wills <swills@FreeBSD.org>
# $FreeBSD$

PORTNAME=	ksshaskpass
PORTVERSION=	0.5.3
PORTREVISION=	5
CATEGORIES=	deskutils
MASTER_SITES=	http://kde-apps.org/CONTENT/content-files/
DISTNAME=	50971-${PORTNAME}-${PORTVERSION}

MAINTAINER=	swills@FreeBSD.org
COMMENT=	KDE 4 version of ssh-askpass with KWallet support

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}
USES=		cmake
USE_KDE4=	kdelibs automoc4
USE_QT4=	moc_build uic_build qmake_build rcc_build

SUB_FILES=	pkg-message

.include <bsd.port.mk>
