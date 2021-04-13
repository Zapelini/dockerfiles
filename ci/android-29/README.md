# Android SDK CI

[![Docker Hub](https://img.shields.io/badge/Docker%20Hub-info-blue.svg)](https://hub.docker.com/r/izapelini/android-sdk-ci)
[![Docker Pulls](https://img.shields.io/docker/pulls/izapelini/android-sdk-ci.svg)](https://hub.docker.com/r/izapelini/android-sdk-ci/)
[![Image Size & Layers](https://images.microbadger.com/badges/image/izapelini/android-sdk-ci.svg)](https://microbadger.com/images/izapelini/android-sdk-ci)

## Included
* OpenJDK 8
* Gradle 6.8.3
* Android SDK (android-29)
* Android Build-tools (29.0.3)
* Android Support Libraries
* Git

## Build image

```bash
docker build -t izapelini/android-sdk-ci .
```

## Run docker

```bash
docker run --rm -it izapelini/android-sdk-ci bash
```
