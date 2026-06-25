FROM ubuntu:22.04 AS builder

ARG TARGETPLATFORM
ARG GRAAL_VERSION=25.0.1
ARG JAVA_VERSION=25

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends curl ca-certificates tar


RUN case "${TARGETPLATFORM}" in \
         "linux/amd64")  ARCH=x64  ;; \
         "linux/arm64")  ARCH=aarch64  ;; \
    esac \
    && mkdir -p /opt/java/graalvm \
    && curl --retry 3 -Lfso /tmp/graalvm.tar.gz https://download.oracle.com/graalvm/${JAVA_VERSION}/archive/graalvm-jdk-${GRAAL_VERSION}_linux-${ARCH}_bin.tar.gz \
    && tar -xf /tmp/graalvm.tar.gz -C /opt/java/graalvm --strip-components=1

FROM ubuntu/chiseled:22.04-base

LABEL maintainer="RikoDEV <kontakt@riko.dev>"


COPY --from=builder /bin/bash /bin/bash
COPY --from=builder /bin/sh /bin/sh
COPY --from=builder /bin/tar /bin/tar
COPY --from=builder /usr/bin/curl /usr/bin/curl
COPY --from=builder /usr/bin/git /usr/bin/git
COPY --from=builder /usr/bin/openssl /usr/bin/openssl
COPY --from=builder /lib /lib
COPY --from=builder /lib64 /lib64
COPY --from=builder /usr/lib /usr/lib


COPY --from=builder /opt/java/graalvm /opt/java/graalvm


ENV JAVA_HOME=/opt/java/graalvm \
    PATH="/opt/java/graalvm/bin:$PATH" \
    LANG='en_US.UTF-8' \
    LANGUAGE='en_US:en' \
    LC_ALL='en_US.UTF-8'


RUN echo "container:x:999:999::/home/container:/bin/bash" >> /etc/passwd && \
    echo "container:x:999:" >> /etc/group && \
    mkdir -p /home/container && \
    chown -R 999:999 /home/container

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./../entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]
