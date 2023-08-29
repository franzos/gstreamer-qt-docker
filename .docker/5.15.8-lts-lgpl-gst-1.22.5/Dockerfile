FROM carlonluca/qt-dev:5.15.8-lts-lgpl

WORKDIR /usr/src

RUN apt update && \
    apt install -y \
    python3-dev python3-distro python3-setuptools python3-pip \
    autotools-dev automake autoconf autopoint \
    libtool \
    g++ \
    make cmake pkg-config \
    bison \
    flex \
    nasm \
    libxv-dev \
    libx11-dev \
    libx11-xcb-dev \
    libpulse-dev \
    gettext \
    libxext-dev \
    libxi-dev \
    x11proto-record-dev \
    libxrender-dev \
    libgl1-mesa-dev \
    libxfixes-dev \
    libxdamage-dev \
    libxcomposite-dev \
    libasound2-dev \
    build-essential \
    gperf \
    wget \
    libxtst-dev \
    libxrandr-dev \
    libglu1-mesa-dev \
    libegl1-mesa-dev \
    git \
    xutils-dev \
    intltool \
    ccache \
    libssl-dev \
    libjson-glib-1.0-0 \
    libjson-glib-dev \
    ninja-build

RUN pip3 install meson==0.62.2 hotdoc==0.13.7 ninja tomli

ENV QT_ANDROID_ROOT=/opt/Qt-android-5.15.8-lts-lgpl
ENV QT_ANDROID_ROOT_DIR=/opt/Qt-android-5.15.8-lts-lgpl
ENV QMAKE=/opt/Qt-android-5.15.8-lts-lgpl/bin/qmake
ENV OPENSSL_ROOT_DIR=/opt/android_openssl/ssl_1.1

COPY ./ninja-1.11.1.tar.gz /root/.cache/cerbero-sources/ninja-1.11.1/v1.11.1.tar.gz
COPY ./proxy-libintl-0.1.tar.gz /root/.cache/cerbero-sources/proxy-libintl-0.1/0.1.tar.gz
COPY ./graphene-1.10.2.tar.gz /root/.cache/cerbero-sources/graphene-1.10.2/1.10.2.tar.gz
COPY ./wavpack-5.4.0.tar.gz /root/.cache/cerbero-sources/wavpack-5.4.0/5.4.0.tar.gz
COPY ./libvpx-v1.12.0.tar.gz /root/.cache/cerbero-sources/libvpx-v1.12.0/v1.12.0.tar.gz
COPY ./openjpeg-2.3.1.tar.gz /root/.cache/cerbero-sources/openjpeg-2.3.1/v2.3.1.tar.gz
COPY ./openh264-2.3.0.tar.gz /root/.cache/cerbero-sources/openh264-2.3.0/v2.3.0.tar.gz
COPY ./srt-1.4.3.tar.gz /root/.cache/cerbero-sources/srt-1.4.3/v1.4.3.tar.gz

RUN git clone https://gitlab.freedesktop.org/gstreamer/cerbero.git /vendor/cerbero && \
    cd /vendor/cerbero && git checkout 1.22.5 && \
    ./cerbero-uninstalled -c config/cross-android-universal.cbc fetch-bootstrap && \
    ./cerbero-uninstalled -c config/cross-android-universal.cbc fetch-package gstreamer-1.0
RUN cd /vendor/cerbero && ./cerbero-uninstalled -c config/cross-android-universal.cbc bootstrap --offline && \
    QMAKE=/opt/Qt-android-5.15.8-lts-lgpl/bin/qmake ./cerbero-uninstalled -c config/cross-android-universal.cbc -v qt5 package gstreamer-1.0 --offline

ENTRYPOINT [ "" ]