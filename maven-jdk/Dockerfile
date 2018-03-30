FROM ubuntu:16.04

LABEL maintainer.name="Mateusz Was"
LABEL maintainer.email="mateusz.was@tomtom.com"

# Install JDK 9 from Oracle (JavaFX included)
RUN set -ex && \
    apt-get update && \
    apt-get install -y --no-install-recommends software-properties-common && \
    add-apt-repository -y ppa:webupd8team/java && \
    apt-get update && \
    # We need to pre-accept Oracle license:
    echo oracle-java9-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-get install -y --no-install-recommends oracle-java9-installer && \
    apt-get install -y --no-install-recommends maven && \
    # Clean all useless data
    apt-get purge && apt-get clean && \
    rm -rf /var/lib/apt/lists/* /var/cache/oracle-jdk9-installer
