# Created by: Marcus Glocker <marcus@nazgul.ch>
# $FreeBSD$

PORTNAME=	wmwlmon
PORTVERSION=	1.0
CATEGORIES=	net windowmaker
MASTER_SITES=	http://www.nazgul.ch/dev/
DISTNAME=	wmwlmon-${PORTVERSION}

MAINTAINER=	LukeD@pobox.com
COMMENT=	DockApp showing the state of a wireless network device

USE_XORG=	x11 xpm

PLIST_FILES=	bin/wmwlmon man/man1/wmwlmon.1.gz

.include <bsd.port.pre.mk>

.if ${OSVERSION} >= 700052
EXTRA_PATCHES=	${PATCHDIR}/extra-patch-wl.c ${PATCHDIR}/extra-patch-wmwlmon.1
pre-everything::
	@${ECHO_CMD} "==========================================================="
	@${ECHO_CMD} "On FreeBSD > 700052 there is no wi(4) support in ${PORTNAME}"
	@${ECHO_CMD} "==========================================================="
.endif

post-patch:
	${REINPLACE_CMD} -e 's#/usr/X11R6#${LOCALBASE}#g' \
		-e 's#/usr/local#${LOCALBASE}#g' ${WRKSRC}/Makefile

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/wmwlmon ${STAGEDIR}${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/wmwlmon.1 ${STAGEDIR}${MANPREFIX}/man/man1

.include <bsd.port.post.mk>
