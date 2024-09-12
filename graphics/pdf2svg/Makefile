# $OpenBSD$

COMMENT =	convert PDF files to SVG

GH_ACCOUNT =	dawbarton
GH_PROJECT =	pdf2svg
GH_TAGNAME =	v0.2.3

CATEGORIES =	graphics

MAINTAINER =	Bjoern Gohla <b.gohla@unix.net>

# GPLv2+
PERMIT_PACKAGE =	Yes

WANTLIB += c cairo glib-2.0 gobject-2.0 intl poppler-glib

LIB_DEPENDS +=	graphics/cairo \
		print/poppler

SEPARATE_BUILD =	Yes
USE_GMAKE =		Yes
CONFIGURE_STYLE =	gnu

.include <bsd.port.mk>
