# $FreeBSD$

PORTNAME=	riscv-fesvr
PORTVERSION=	0.0.1
PORTREVISION=	20170206
CATEGORIES=	emulators

MAINTAINER=	lwhsu@FreeBSD.org
COMMENT=	RISC-V Frontend Server

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

USE_GITHUB=	yes
GH_ACCOUNT=	freebsd-riscv
GH_TAGNAME=	10a0333

USES=	gmake
HAS_CONFIGURE=	yes
USE_LDCONFIG=	yes

.include <bsd.port.pre.mk>

post-patch:
	${REINPLACE_CMD} -e \
	's|[(]install_libs_dir[)]/pkgconfig|(INSTALLDIR)/libdata/pkgconfig|g' \
	${WRKSRC}/Makefile.in

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/lib/libfesvr.so
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/elf2hex

.include <bsd.port.post.mk>
