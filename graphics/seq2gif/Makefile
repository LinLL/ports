# $FreeBSD$

PORTNAME=	seq2gif
PORTVERSION=	0.10.3.20140802
#PORTEPOCH=	0
CATEGORIES=	graphics

MAINTAINER=	sue@iwmt.org
COMMENT=	Convert a ttyrec record into a gif animation directly

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

USE_GITHUB=	yes
GH_ACCOUNT=	saitoha
#GH_TAGNAME=	v${PORTVERSION}
GH_TAGNAME=	${GH_COMMIT}
GH_COMMIT=	253dacb

USE_LDCONFIG=	yes
USES=		libtool

GNU_CONFIGURE=	yes
#CONFIGURE_ARGS=	--with-pkgconfigdir=${LOCALBASE}/libdata/pkgconfig

INSTALL_TARGET=	install-strip

PORTDOCS=	README.md

PLIST_FILES=	bin/seq2gif

post-install:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README.md ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
