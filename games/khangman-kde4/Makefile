# $FreeBSD$

PORTNAME=	khangman
PORTVERSION=	${KDE4_VERSION}
PORTREVISION=	3
CATEGORIES=	games kde kde-kde4

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Hangman game for KDE 4

USES=		cmake:outsource kde:4 tar:xz
USE_KDE=	kdelibs libkdeedu automoc4
USE_QT4=	corelib declarative gui opengl script xml \
		moc_build qmake_build rcc_build uic_build
USE_LDCONFIG=	yes

.include <bsd.port.mk>
