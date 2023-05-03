ARG JDK_VERSION=19
ARG JDK_IMAGE=amazoncorretto:${JDK_VERSION}
FROM ${JDK_IMAGE} AS metrics-reporter

ARG VERSION=0.40.9

ENV APPLICATION airbyte-metrics-reporter
ENV VERSION ${VERSION}

RUN yum update --security -y && yum clean all

WORKDIR /app

ADD bin/${APPLICATION}-${VERSION}.tar /app


# wait for upstream dependencies to become available before starting server
ENTRYPOINT ["/bin/bash", "-c", "${APPLICATION}-${VERSION}/bin/${APPLICATION}"]
