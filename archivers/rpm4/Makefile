# Created by: Greg Lewis <glewis@FreeBSD.org>
# $FreeBSD$

PORTNAME=	rpm
PORTVERSION=	4.12.0.1
PORTREVISION=	1
CATEGORIES=	archivers
MASTER_SITES=	http://rpm.org/releases/rpm-${PORTVERSION:R:R}.x/ \
		ftp://ftp.mirrorservice.org/sites/ftp.rpm.org/pub/rpm/dist/rpm-${PORTVERSION:E}.x/
PKGNAMESUFFIX=	4

MAINTAINER=	johans@FreeBSD.org
COMMENT=	The RPM Package Manager

LIB_DEPENDS=	libpopt.so:${PORTSDIR}/devel/popt \
		libnss3.so:${PORTSDIR}/security/nss \
		libdbus-1.so:${PORTSDIR}/devel/dbus
BUILD_DEPENDS=	${LOCALBASE}/bin/gsed:${PORTSDIR}/textproc/gsed

OPTIONS_DEFINE=	PYTHON NLS DOCS
OPTIONS_DEFAULT=PYTHON NLS
OPTIONS_SUB=	yes
PYTHON_CONFIGURE_ENABLE=python
PYTHON_USES=	python:2.7
NLS_CONFIGURE_ENABLE=nls
NLS_USES=	gettext
NLS_LIBS=	-lintl
PORTDOCS=	*

USES=		alias gmake libtool lua:51 pathfix pkgconfig shebangfix \
		tar:bzip2
USE_BDB=	46+
INVALID_BDB_VER=51
GNU_CONFIGURE=	yes
USE_LDCONFIG=	yes
INSTALL_TARGET=	install-strip
CONFLICTS_INSTALL=	rpm-[35].* rpm5-*
SHEBANG_FILES=	scripts/brp-python-bytecompile scripts/check-prereqs \
		scripts/check-rpaths-worker scripts/pythondeps.sh \
		scripts/mono-find-requires scripts/mono-find-provides \
		scripts/pkgconfigdeps.sh scripts/fontconfig.prov \
		scripts/rpmdb_loadcvt \
		scripts/perl.prov scripts/perl.req scripts/perldeps.pl \
		scripts/osgideps.pl scripts/tcl.req \
		python/rpm/transaction.py

CPPFLAGS+=	-I${LOCALBASE}/include \
		-I${LOCALBASE}/include/nspr -I${LOCALBASE}/include/nss/nss \
		-I${BDB_INCLUDE_DIR} -I${LUA_INCDIR}
LDFLAGS+=	-L${LOCALBASE}/lib -L${LOCALBASE}/lib/nss \
		-L${BDB_LIB_DIR} -L${LUA_LIBDIR}
CONFIGURE_ARGS+=--with-external-db \
		--without-db \
		--with-popt-prefix="${LOCALBASE}" \
		--sysconfdir=${PREFIX}/etc \
		--localstatedir=/var \
		--without-javaglue
CONFIGURE_ENV+=	LUA_CFLAGS=-I${LUA_INCDIR} \
		LUA_LIBS="-L${LUA_LIBDIR} -llua-${LUA_VER} -lm"
PLIST_SUB+=	VERSION=${PORTVERSION}

.include <bsd.port.pre.mk>

.if ${OSVERSION} < 1000000
LIB_DEPENDS+=	libarchive.so.13:${PORTSDIR}/archivers/libarchive
.endif

post-patch:
	${REINPLACE_CMD} -e 's:\.\./\.\./bin/::' ${WRKSRC}/Makefile.in
	${REINPLACE_CMD} -e 's/(hpux)/& || defined(__FreeBSD__)/' \
		${WRKSRC}/misc/fts.?
	${REINPLACE_CMD} -e 's/ __GLIBC__.*/& || defined(__FreeBSD__)/' \
		${WRKSRC}/system.h

post-install:
	# Install documentation
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	cd ${WRKSRC}/doc && ${COPYTREE_SHARE} librpm/html ${STAGEDIR}${DOCSDIR}

.include <bsd.port.post.mk>
