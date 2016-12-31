# Created by: Li-Wen Hsu <lwhsu@FreeBSD.org>
# $FreeBSD$

PORTNAME=	gcc
PORTVERSION=	6.1.0
CATEGORIES=	devel
PKGNAMEPREFIX=	riscv-

MAINTAINER=	lwhsu@FreeBSD.org
COMMENT=	Cross GNU Compiler Collection for ${PKGNAMEPREFIX:C/-//g}

LICENSE=	GPLv3

BUILD_DEPENDS=	gawk:lang/gawk \
		gsed:textproc/gsed
LIB_DEPENDS=	libgmp.so:math/gmp \
		libmpfr.so:math/mpfr \
		libmpc.so:math/mpc

USE_GITHUB=	yes
GH_ACCOUNT=	freebsd-riscv
GH_PROJECT=	riscv-gcc
GH_TAGNAME=	095b1d6

USES=	gmake iconv libtool makeinfo

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--target=riscv64-unknown-${OPSYS:tl}${OSREL} \
		--with-sysroot=/ \
		--without-newlib \
		--without-headers \
		--disable-werror \
		--disable-shared \
		--enable-threads \
		--enable-tls \
		--enable-languages=c,c++ \
		--with-gmp=/usr/local \
		--with-mpfr=/usr/local \
		--with-mpc=/usr/local \
		--disable-libatomic \
		--disable-libmudflap \
		--disable-libssp \
		--disable-libquadmath \
		--disable-libgomp \
		--disable-nls \
		--disable-bootstrap \
		--disable-multilib

ALL_TARGET=	inhibit-libc=true all-gcc
INSTALL_TARGET=	inhibit-libc=true install-gcc

.include <bsd.port.pre.mk>

post-install:
	@if [ -d ${STAGEDIR}${PREFIX}/${INFO_PATH} ] ; then ${RM} -r ${STAGEDIR}${PREFIX}/${INFO_PATH}; fi

.include <bsd.port.post.mk>
