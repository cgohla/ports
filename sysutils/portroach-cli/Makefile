# $OpenBSD: Makefile,v 1.3 2021/01/12 13:20:41 kn Exp $

COMMENT =		query portroach(1)
CATEGORIES =		sysutils
DISTFILES =		# empty
# <portroach API>.rev
PKGNAME =		portroach-cli-1.2
MAINTAINER =		Klemens Nanni <kn@openbsd.org>

# ISC
PERMIT_PACKAGE =	Yes

NO_BUILD =		Yes

RUN_DEPENDS =		textproc/jq
TEST_DEPENDS =		devel/shellcheck,-main

SCRIPT =		${FILESDIR}/portroach-cli
MAN =			${SCRIPT}.1

do-install:
	${INSTALL_SCRIPT} ${SCRIPT} ${PREFIX}/bin/
	${INSTALL_MAN} ${MAN} ${PREFIX}/man/man1/

do-test:
	ksh -n ${SCRIPT}
	shellcheck ${SCRIPT}
	mandoc -Tlint ${MAN}

.include <bsd.port.mk>
