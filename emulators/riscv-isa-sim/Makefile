# $FreeBSD$

PORTNAME=	riscv-isa-sim
PORTVERSION=	0.0.1
PORTREVISION=	20170206
CATEGORIES=	emulators

MAINTAINER=	lwhsu@FreeBSD.org
COMMENT=	Spike, a RISC-V ISA Simulator

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libfesvr.so:emulators/riscv-fesvr

USE_GITHUB=	yes
GH_ACCOUNT=	freebsd-riscv
GH_TAGNAME=	11ec3a3

USES=	compiler:c++11-lang gmake pathfix shebangfix
HAS_CONFIGURE=	yes
SHEBANG_FILES=	scripts/vcs-version.sh
USE_LDCONFIG=	yes

LDFLAGS+=	-L${LOCALBASE}/lib
CFLAGS+=	-I${LOCALBASE}/include

STRIP_FILES=	bin/spike \
		bin/spike-dasm \
		bin/termios-xspike \
		bin/xspike \
		lib/libdummy_rocc.so \
		lib/libriscv.so \
		lib/libsoftfloat.so \
		lib/libspike_main.so

post-extract:
	@${MV} ${WRKSRC}/riscv/insn_template.h ${WRKSRC}/riscv/insn_template.hpp

post-install:
.	for f in ${STRIP_FILES}
		${STRIP_CMD} ${STAGEDIR}${PREFIX}/${f}
.	endfor

.include <bsd.port.mk>
