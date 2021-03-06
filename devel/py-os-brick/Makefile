# Created by: Alexander Nusov <alexander.nusov@nfvexpress.com>
# $FreeBSD$

PORTNAME=	os-brick
PORTVERSION=	1.10.0
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	alexander.nusov@nfvexpress.com
COMMENT=	Openstack cinder brick library for managing local volume attaches

LICENSE=	APACHE20

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pbr>=1.8:devel/py-pbr@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}os-win>=1.3.0:devel/py-os-win@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}castellan>=0.4.0:devel/py-castellan@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}six>=1.9.0:devel/py-six@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}retrying>=0:devel/py-retrying@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests>=2.10.0:www/py-requests@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.utils>=3.18.0:devel/py-oslo.utils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.service>=1.10.0:devel/py-oslo.service@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.privsep>=1.9.0:devel/py-oslo.privsep@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.i18n>=2.1.0:devel/py-oslo.i18n@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.serialization>=1.10.0:devel/py-oslo.serialization@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.log>=3.11.0:devel/py-oslo.log@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.concurrency>=3.8.0:devel/py-oslo.concurrency@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}eventlet>=0:net/py-eventlet@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Babel>=2.3.4:devel/py-babel@${PY_FLAVOR}

NO_ARCH=	yes

EXTRA_PATCHES=	${FILESDIR}/01-os-type.patch:-p1 \
		${FILESDIR}/02-nfs.patch:-p1

USES=		python
USE_PYTHON=	autoplist distutils

post-patch:
	@${ECHO_CMD} "os-brick configuration at ${PREFIX}/etc/os-brick/rootwrap.d" >> \
		${WRKSRC}/etc/os-brick.readme
	@${ECHO_CMD} "os-brick configuration" >> ${WRKSRC}/etc/os-brick/info

.include <bsd.port.mk>
