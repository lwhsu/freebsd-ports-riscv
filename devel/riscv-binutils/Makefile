# $FreeBSD$

PORTNAME=	binutils
PORTVERSION=	2.27.51.20161101
CATEGORIES=	devel
PKGNAMEPREFIX=	riscv-

MAINTAINER=	lwhsu@FreeBSD.org
COMMENT=	GNU binutils for RISC-V cross-development

LICENSE=	GPLv3

BUILD_DEPENDS=	gawk:lang/gawk \
		gsed:textproc/gsed
LIB_DEPENDS=	libgmp.so:math/gmp \
		libmpfr.so:math/mpfr \
		libmpc.so:math/mpc

USE_GITHUB=	yes
GH_ACCOUNT=	freebsd-riscv
GH_PROJECT=	riscv-binutils-gdb
GH_TAGNAME=	6da6b8c

USES=	bison gmake libtool makeinfo

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--target=riscv64-${OPSYS:tl} \
		--with-sysroot=/ \
		--disable-gdb \
		--disable-sim \
		--enable-tls \
		--disable-werror \
		--disable-nls \
		--disable-shared \

.include <bsd.port.pre.mk>

post-install:
	@if [ -d ${STAGEDIR}${PREFIX}/${INFO_PATH} ] ; then ${RM} -r ${STAGEDIR}${PREFIX}/${INFO_PATH}; fi

.include <bsd.port.post.mk>
