# Created by: Anton Berezin <tobez@tobez.org>
# $FreeBSD$

PORTNAME=	Cache-Cache
PORTVERSION=	1.07
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	perl@FreeBSD.org
COMMENT=	Perl Cache interface

LICENSE=	ART10 GPLv1
LICENSE_COMB=	dual

BUILD_DEPENDS=	p5-Cache>=0:${PORTSDIR}/devel/p5-Cache \
		p5-Digest-SHA1>=2.02:${PORTSDIR}/security/p5-Digest-SHA1 \
		p5-Error>=0.15:${PORTSDIR}/lang/p5-Error \
		p5-IPC-ShareLite>=0.09:${PORTSDIR}/devel/p5-IPC-ShareLite
RUN_DEPENDS:=	${BUILD_DEPENDS}

USES=		perl5
USE_PERL5=	configure

.include <bsd.port.mk>
