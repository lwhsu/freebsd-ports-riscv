# $FreeBSD$

PORTNAME=	riscv-isa-sim
PORTVERSION=	0.0.1
PORTREVISION=	20170206
CATEGORIES=	emulators

MAINTAINER=	sbruno@FreeBSD.org
COMMENT=	Spike, a RISC-V ISA Simulator

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libfesvr.so:emulators/riscv-fesvr

USE_GITHUB=	yes
GH_ACCOUNT=	freebsd-riscv
GH_TAGNAME=	11ec3a3

USES=		gmake shebangfix compiler:c++11-lang
HAS_CONFIGURE=	yes
SHEBANG_FILES=	scripts/vcs-version.sh
USE_LDCONFIG=	yes

LDFLAGS+=	-L${LOCALBASE}/lib
CFLAGS+=	-I${LOCALBASE}/include

post-extract:
	@${MV} ${WRKSRC}/riscv/insn_template.h ${WRKSRC}/riscv/insn_template.hpp

.include <bsd.port.mk>
