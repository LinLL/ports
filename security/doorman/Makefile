# Created by: Aaron Dalton <aaron@daltons.ca>
# $FreeBSD$

PORTNAME=	doorman
PORTVERSION=	0.81
PORTREVISION=	1
CATEGORIES=	security
MASTER_SITES=	SF/${PORTNAME}/${PORTNAME}/${PORTNAME}-${PORTVERSION}
EXTRACT_SUFX=	.tgz

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Port knocking implementation, both daemon and client

BUILD_DEPENDS=	lsof:${PORTSDIR}/sysutils/lsof
RUN_DEPENDS:=	${BUILD_DEPENDS}

PATCH_STRIP=	-p1

GNU_CONFIGURE=	yes
INSTALL_TARGET=	installdirs install-exec install-data

SUB_FILES=	pkg-message doormand.cf.EXAMPLE
USE_RC_SUBR=	doorman

pre-patch:
	@${REINPLACE_CMD} -e 's/[[:cntrl:]]*$$//' \
		${WRKSRC}/doormand.c

post-install:
	${RM} -f ${STAGEDIR}${PREFIX}/etc/doormand/ipf_add
	(cd ${FILESDIR} && ${INSTALL_SCRIPT} ipf_add.atend ipf_delete \
		ipf_add.before_block ${STAGEDIR}${PREFIX}/etc/doormand)
	${INSTALL_DATA} ${WRKDIR}/doormand.cf.EXAMPLE \
		${STAGEDIR}${PREFIX}/etc/doormand
	${INSTALL_MAN} -C ${WRKSRC}/knock.1 ${STAGEDIR}${PREFIX}/man/man1
	(cd ${WRKSRC} && ${INSTALL_MAN} -C knockcf.5 doormand.cf.5 guestlist.5 \
		${STAGEDIR}${PREFIX}/man/man5)
	${INSTALL_MAN} -C ${WRKSRC}/doormand.8 ${STAGEDIR}${PREFIX}/man/man8

.include <bsd.port.mk>
