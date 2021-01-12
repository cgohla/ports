# $OpenBSD: Makefile.template,v 1.88 2020/05/15 01:32:48 abieber Exp $

COMMENT =	convert TikZ environments to SVG files

VERSION =	0.1.2

GITLAB_PROJECT =	tikztosvg
GITLAB_TAG =		v${VERSION}
GITLAB_ACCOUNT =	pablo-escobar
GITLAB_MASTER_SITES =	https://gitlab.com/${GITLAB_ACCOUNT}/${GITLAB_PROJECT}/-/archive/${GITLAB_TAG}/
GITLAB_DISTFILES =	${DISTNAME}.tar.gz

EXECUTABLE_NAME =	${GITLAB_PROJECT}

DISTNAME =	${GITLAB_PROJECT}-${GITLAB_TAG}
PKGNAME =	${GITLAB_PROJECT}-${VERSION}

CATEGORIES =	graphics
HOMEPAGE =	https://ctan.org/pkg/tikztosvg
MAINTAINER =	Bjoern Gohla <b.gohla@unix.net>

# License GPL v3
PERMIT_PACKAGE =	Yes

MASTER_SITES =		${GITLAB_MASTER_SITES}
DISTFILES =		${GITLAB_DISTFILES}

NO_BUILD =	Yes
NO_TEST =	Yes
PKG_ARCH =	*

RUN_DEPENDS += 	graphics/pdf2svg \
		print/texlive/texmf,-main

SEPARATE_BUILD =	Yes
CONFIGURE_SCRIPT =

DOC_DIR =	${PREFIX}/share/doc/${PKGNAME}

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${EXECUTABLE_NAME} \
		${PREFIX}/bin/${EXECUTABLE_NAME}
	${INSTALL_MAN} ${WRKSRC}/man/${EXECUTABLE_NAME}.1 \
		${PREFIX}/man/man1/${EXECUTABLE_NAME}.1
	${INSTALL_DATA_DIR} ${DOC_DIR}
	${INSTALL_DATA} ${WRKSRC}/${EXECUTABLE_NAME}.pdf ${DOC_DIR}

.include <bsd.port.mk>
