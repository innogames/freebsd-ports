# $FreeBSD$

PORTNAME=	Kvantum
PORTVERSION=	0.10.5
PORTREVISION=	1
DISTVERSIONPREFIX=	V
CATEGORIES=	x11-themes
PKGNAMEPREFIX=	qt5-style-

MAINTAINER=	rezny@FreeBSD.org
COMMENT=	SVG-based theme engine for Qt4/5, KDE and LXQT

LICENSE=	GPLv3+
LICENSE_FILE=	${WRKSRC}/COPYING

USE_GITHUB=	yes
GH_ACCOUNT=	tsujan

USES=		compiler:c++11-lang qmake qt:5
USE_QT=		core gui svg widgets x11extras buildtools_build linguisttools_build
USE_XORG=	x11 xext
USE_GL=		gl

WRKSRC_SUBDIR=	${PORTNAME}

post-patch:
	@${REINPLACE_CMD} -e 's|/kde4/|/|g' ${WRKSRC}/style/style.pro
	@${REINPLACE_CMD} -e 's|/kde4/|/|g' -e 's|--no-preserve=mode||g' \
		${WRKSRC}/themes/themes.pro

.include <bsd.port.mk>
