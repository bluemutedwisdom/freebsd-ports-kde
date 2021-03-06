# $FreeBSD$

PORTNAME=	webengine
PORTREVISION=	2
CATEGORIES=	www devel python

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Python bindings for the Qt5 toolkit, QtWebEngine module

# LICENSE set in Mk/Uses/pyqt.mk

USES=		python pyqt:5
USE_GL=		gl
USE_PYQT=	sip_build core_run gui_run network_run webchannel_run
USE_PYTHON=	flavors
USE_QT5=	core gui location network printsupport qml quick webchannel \
		webengine widgets qmake_build

CONFIGURE_ARGS=	--enable QtWebEngine \
		--enable QtWebEngineCore \
		--enable QtWebEngineWidgets \
		--no-stubs
PYQT_DIST=	yes

OPTIONS_DEFINE=		API DEBUG
OPTIONS_DEFAULT=	API
OPTIONS_SUB=		yes

API_DESC=		Install QtWebEngine API for QScintilla2
API_CONFIGURE_ON=	--qsci-api --qsci-api-destdir=${QSCIDIR}
API_CONFIGURE_OFF=	--no-qsci-api
API_LIB_DEPENDS=	libqscintilla2_qt5.so:devel/qscintilla2-qt5
DEBUG_CONFIGURE_ON=	--debug --trace

post-install-DEBUG-off:
	${STRIP_CMD} ${STAGEDIR}${PYTHON_SITELIBDIR}/PyQt5/QtWebEngine*.so

.include <bsd.port.mk>
