# Created by: Vanilla I. Shu <vanilla@MinJe.com.TW>
# $FreeBSD$

PORTNAME=	amp
PORTVERSION=	0.7.6
PORTEPOCH=	1
CATEGORIES=	audio
MASTER_SITES=	http://www.gufi.org/ports/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Another mp3 player

DEPRECATED=	No more upstream
EXPIRATION_DATE=	2018-03-01

USES=		gmake
GNU_CONFIGURE=	yes
CONFIGURE_ENV=	ac_cv_prog_gcc=no

PLIST_FILES=	bin/amp man/man1/amp.1.gz

post-patch:
	@${REINPLACE_CMD} -e \
		'/CC="gcc"/s|^|#| ; \
		 /CFLAGS=$$/s|^|#| ; \
		 s|-O6|$$CFLAGS|' ${WRKSRC}/configure

do-install:
	(cd ${WRKSRC} && ${INSTALL_PROGRAM} amp ${STAGEDIR}${PREFIX}/bin)
	(cd ${WRKSRC} && ${INSTALL_MAN} amp.1 ${STAGEDIR}${PREFIX}/man/man1)

.include <bsd.port.mk>
