# Created by: Emanuel Haupt <ehaupt@FreeBSD.org>
# $FreeBSD$

PORTNAME=	shuffle-db
DISTVERSION=	1.0-rc1
CATEGORIES=	misc
MASTER_SITES=	SF/${PORTNAME}/rebuild_db/1.0-rc1
DISTNAME=	rebuild_db-${DISTVERSION}

MAINTAINER=	ehaupt@FreeBSD.org
COMMENT=	IPod shuffle database builder

USES=		python
NO_BUILD=	yes

WRKSRC=		${WRKDIR}/rebuild_db
PLIST_FILES=	bin/rebuild_db.py

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/rebuild_db.py ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>
