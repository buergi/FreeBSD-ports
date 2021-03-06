# Created by: roland.jesse@gmx.net
# $FreeBSD$

PORTNAME=	SoQt
PORTVERSION=	1.5.0
PORTREVISION=	6
CATEGORIES=	x11-toolkits
MASTER_SITES=	https://bitbucket.org/Coin3D/coin/downloads/
DIST_SUBDIR=	KDE

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Qt4 toolkit library for Coin

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/LICENSE.GPL

DEPRECATED=		Qt4 has been EOL since december 2015
EXPIRATION_DATE=	2019-03-15

LIB_DEPENDS=	libCoin.so:graphics/Coin

USES=		gmake libtool pathfix pkgconfig qmake:no_env qt:4
USE_QT=		corelib opengl moc_build
USE_GL=		gl
GNU_CONFIGURE=	yes
CONFIGURE_ENV=	QTDIR="${PREFIX}" MOC="${MOC}"
CONFIGURE_ARGS=	--with-pthread=yes --with-coin=${LOCALBASE} \
		--with-qt=${QT_LIBDIR} \
		--enable-debug=no
INSTALL_TARGET=	install-strip
USE_LDCONFIG=	yes

CPPFLAGS+=	-I${QT_INCDIR}/Qt -I${QT_INCDIR} -I${LOCALBASE}/include
LDFLAGS+=	-L${QT_LIBDIR} -L${LOCALBASE}/lib

post-patch:
	@${REINPLACE_CMD} -e \
		'/LDFLAGS/s| $$sim_ac_coin_ldflags|| ; \
		 /CXXFLAGS/s| -fno-for-scope||' ${WRKSRC}/configure

post-install:
	@${TOUCH} ${STAGEDIR}${PREFIX}/include/Inventor/Qt/engines/.keep_me

.include <bsd.port.mk>
