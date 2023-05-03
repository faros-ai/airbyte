ARG JDK_VERSION=19
ARG JDK_IMAGE=amazoncorretto:${JDK_VERSION}
FROM ${JDK_IMAGE}

ARG VERSION=0.40.9

ENV APPLICATION airbyte-bootloader
ENV VERSION ${VERSION}

RUN yum update --security -y && yum clean all

WORKDIR /app

ADD bin/${APPLICATION}-${VERSION}.tar /app


ENTRYPOINT ["/bin/bash", "-c", "${APPLICATION}-${VERSION}/bin/${APPLICATION}"]
