FROM alvrme/alpine-android:android-29

LABEL maintainer "ivanilsonz@gmail.com"

ENV SDK_HOME /opt

# Gradle
ENV GRADLE_VERSION 6.8.3
ENV GRADLE_SDK_URL https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-all.zip

RUN apk add openssh git \
    && wget "${GRADLE_SDK_URL}" -O gradle-${GRADLE_VERSION}-all.zip \
    && unzip gradle-${GRADLE_VERSION}-all.zip -d ${SDK_HOME} \
    && rm -rf gradle-${GRADLE_VERSION}-all.zip

ENV GRADLE_HOME ${SDK_HOME}/gradle-${GRADLE_VERSION}
ENV PATH ${GRADLE_HOME}/bin:$PATH