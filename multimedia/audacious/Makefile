# Created by: Zastupov Stepan [RedChrom] <redchrom@mail.ru>
# $FreeBSD$

PORTNAME=	audacious
PORTVERSION=	3.9
PORTREVISION=	1
CATEGORIES=	multimedia audio
MASTER_SITES=	http://distfiles.audacious-media-player.org/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Lightweight and versatile audio player

LICENSE=	BSD2CLAUSE BSD3CLAUSE
LICENSE_COMB=	multi
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libfreetype.so:print/freetype2 \
		libfontconfig.so:x11-fonts/fontconfig

CONFLICTS_INSTALL=	audacious-gtk3-3.*

SUB_FILES=	pkg-message

USES=		compiler:c++11-lib desktop-file-utils gettext-tools gmake \
		localbase pkgconfig tar:bzip2
GNU_CONFIGURE=	yes
USE_XORG=	x11 sm
USE_GNOME=	gtk20 glib20 cairo
USE_LDCONFIG=	yes
INSTALLS_ICONS=	yes

CONFIGURE_ARGS=	--with-pkgconfigdir=${PREFIX}/libdata/pkgconfig \
		--enable-gtk \
		--without-buildstamp

OPTIONS_DEFINE=	ICONV NLS EXECINFO
OPTIONS_DEFAULT=ICONV EXECINFO
ICONV_USES=	iconv
NLS_USES=	gettext-runtime
NLS_CONFIGURE_OFF=	--disable-nls
NLS_EXTRA_PATCHES_OFF=	${FILESDIR}/extra-patch-Makefile
OPTIONS_SUB=	yes
EXECINFO_DESC=	Build with libexecinfo support

post-patch:
	@${REINPLACE_CMD} -e 's| $${MFLAGS}||g' \
		${WRKSRC}/buildsys.mk.in

post-patch-EXECINFO-on:
	@${REINPLACE_CMD} 's|-lm |-lm -lexecinfo |' \
		${WRKSRC}/src/audacious/Makefile
	@${REINPLACE_CMD} 's|-laudcore|-laudcore -lexecinfo|' \
		${WRKSRC}/audacious.pc.in

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/aud*
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/lib/lib*

.include <bsd.port.mk>
