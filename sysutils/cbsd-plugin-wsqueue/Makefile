# $FreeBSD:$

PORTNAME=	cbsd-plugin-wsqueue
PORTVERSION=	0.1
CATEGORIES=	sysutils

MAINTAINER=	olevole@olevole.ru
COMMENT=	CBSD WEB UI

LICENSE=	BSD
RUN_DEPENDS=	cbsd:sysutils/cbsd
USES=		go

SUB_FILES=	pkg-message

PLIST_FILES=	cbsd/modules/cbsd_queue.d/wsclonos-sendqueue \
		cbsd/modules/cbsd_queue.d/securecmd \
		cbsd/modules/cbsd_queue.d/cbsd_queue_sys \
		cbsd/modules/cbsd_queue.d/cbsd_queue

USE_GITHUB=	yes
GH_TAGNAME=	73b05d7
GH_ACCOUNT=	cbsd
GH_PROJECT=	cbsd-plugin-wsqueue

GH_TUPLE=	go-logfmt:logfmt:v0.3.0:go_logfmt/src/github.com/go-logfmt/logfmt \
		gorilla:websocket:v1.4.0:websocket/src/github.com/gorilla/websocket

post-extract:
	${LN} -sf ${WRKSRC}/src ${WRKDIR}
	${LN} -sf ${WRKSRC} ${WRKDIR}/src/${PORTNAME}

do-install:
	${MKDIR} ${STAGEDIR}${PREFIX}/cbsd
	${MKDIR} ${STAGEDIR}${PREFIX}/cbsd/modules
	${MKDIR} ${STAGEDIR}${PREFIX}/cbsd/modules/cbsd_queue.d
	${INSTALL_PROGRAM} ${WRKDIR}/bin/${PORTNAME} ${STAGEDIR}${PREFIX}/cbsd/modules/cbsd_queue.d/wsclonos-sendqueue
	${CP} ${WRKSRC}/cbsd_queue ${STAGEDIR}${PREFIX}/cbsd/modules/cbsd_queue.d/cbsd_queue
	${CP} ${WRKSRC}/cbsd_queue_sys ${STAGEDIR}${PREFIX}/cbsd/modules/cbsd_queue.d/cbsd_queue_sys
	${CP} ${WRKSRC}/securecmd ${STAGEDIR}${PREFIX}/cbsd/modules/cbsd_queue.d/securecmd


.include <bsd.port.mk>
