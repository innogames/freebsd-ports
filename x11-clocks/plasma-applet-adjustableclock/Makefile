# $FreeBSD$

PORTNAME=	adjustableclock
PORTVERSION=	4.1.4
PORTREVISION=	5
CATEGORIES=	x11-clocks deskutils kde
MASTER_SITES=	http://kde-look.org/CONTENT/content-files/
PKGNAMEPREFIX=	plasma-applet-
DISTNAME=	92825-${PORTNAME}-${PORTVERSION}

MAINTAINER=	jhale@FreeBSD.org
COMMENT=	KDE4 highly configurable clock plasma applet

LICENSE=	GPLv2

USES=		cmake gettext kde:4 qt:4 tar:bzip2
USE_KDE=	automoc4 workspace
USE_QT=		qmake_build moc_build rcc_build uic_build

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}

.include <bsd.port.mk>
