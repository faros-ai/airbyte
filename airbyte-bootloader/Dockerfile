ARG JDK_VERSION=17-al2023
ARG JDK_IMAGE=amazoncorretto:${JDK_VERSION}
FROM ${JDK_IMAGE}

ARG VERSION=0.40.9

ENV APPLICATION airbyte-bootloader
ENV VERSION ${VERSION}

RUN dnf update --security -y && dnf clean all

WORKDIR /app

ADD bin/${APPLICATION}-${VERSION}.tar /app


ENTRYPOINT ["/bin/bash", "-c", "${APPLICATION}-${VERSION}/bin/${APPLICATION}"]
