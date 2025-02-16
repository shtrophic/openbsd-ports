COMMENT =		get Signal notifications via UnifiedPush

DIST_TUPLE +=		github mollyim mollysocket 1.6.0 .

CATEGORIES =		net

HOMEPAGE =		https://github.com/mollyim/mollysocket

# AGPL-3.0-or-later
PERMIT_PACKAGE =	Yes

LIB_DEPENDS =		databases/sqlite3

WANTLIB =		${MODCARGO_WANTLIB} m ssl crypto sqlite3

MODULES =		devel/cargo
MODCARGO_RUSTFLAGS =	-C debuginfo=0

CONFIGURE_STYLE =	cargo

SEPARATE_BUILD =	Yes

do-install:
	${INSTALL_PROGRAM} ${MODCARGO_TARGET_DIR}/release/mollysocket ${PREFIX}/bin/

	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/mollysocket
	${INSTALL_DATA} ${WRKSRC}/config-sample.toml \
		${PREFIX}/share/examples/mollysocket/mollysocket.conf

.include "crates.inc"

.include <bsd.port.mk>
