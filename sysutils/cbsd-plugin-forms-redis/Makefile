# $FreeBSD:$

PORTNAME=	cbsd-plugin-forms-redis
PORTVERSION=	0.1
CATEGORIES=	sysutils

MAINTAINER=	olevole@olevole.ru
COMMENT=	CBSD WEB UI

LICENSE=	BSD

RUN_DEPENDS=	cbsd:sysutils/cbsd

USE_GITHUB=	yes
GH_TAGNAME=	05d1f74
GH_ACCOUNT=	cbsd
GH_PROJECT=	cbsd-plugin-forms-redis

NO_BUILD=	yes
NO_ARCH=	yes
TARGET_DIR=	${PREFIX}/cbsd/modules/forms.d/redis

do-install:
	${MKDIR} ${STAGEDIR}${TARGET_DIR}
	cd ${WRKSRC} && ${RM} .gitignore .gitmodules .travis.yml
	cd ${WRKSRC} && ${CP} -a . ${STAGEDIR}${TARGET_DIR}/

post-install:
	@${FIND} -s ${STAGEDIR}${TARGET_DIR} -not -type d | ${SORT} | \
		${SED} -e 's#^${STAGEDIR}${PREFIX}/##' >> ${TMPPLIST}


.include <bsd.port.mk>
