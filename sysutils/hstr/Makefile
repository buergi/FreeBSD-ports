# Created by: Patrice Clement <monsieurp@gentoo.org>
# $FreeBSD$

PORTNAME=	hstr
DISTVERSION=	2.0
CATEGORIES=	sysutils

MAINTAINER=	monsieurp@gentoo.org
COMMENT=	Bash and Zsh shell history suggest box

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	pkg-config:devel/pkgconf

USES=	autoreconf ncurses readline
USE_GITHUB=	yes
GH_ACCOUNT=	dvorka
GH_PROJECT=	hstr

GNU_CONFIGURE=	yes

PLIST_FILES=	bin/hh bin/hstr \
		man/man1/hstr.1.gz share/bash-completion/completions/hstr

.include <bsd.port.mk>
