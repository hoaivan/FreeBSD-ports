# $FreeBSD$

PORTNAME=	gotop
DISTVERSION=	1.7.1
CATEGORIES=	sysutils

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Terminal based graphical activity monitor inspired by gtop and vtop

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/src/github.com/${GH_ACCOUNT}/${PORTNAME}/LICENSE

BUILD_DEPENDS=	go:lang/go

USE_GITHUB=	nodefault # the main code is in GH_TUPLE
GH_ACCOUNT=	cjbassi
GH_TUPLE=	cjbassi:gotop:${DISTVERSIONFULL}:main/src/github.com/cjbassi/gotop \
		cjbassi:termui:e8dd23f:termui/src/github.com/cjbassi/termui \
		docopt:docopt.go:ee0de3b:docopt/src/github.com/docopt/docopt-go \
		shirou:gopsutil:v2.18.11:gopsutil/src/github.com/shirou/gopsutil \
		golang:sys:37707fd:sys/src/golang.org/x/sys
GH_SUBDIR=	src/github.com/${GH_ACCOUNT}/${PORTNAME}

PLIST_FILES=	bin/${PORTNAME}

do-build:
	@cd ${WRKSRC}/src/github.com/${GH_ACCOUNT}/${PORTNAME} && \
		${SETENV} ${MAKE_ENV} GOPATH=${WRKSRC} go install ./...

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/${PORTNAME} ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>
