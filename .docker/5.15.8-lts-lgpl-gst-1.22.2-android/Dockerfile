FROM carlonluca/qt-dev:5.15.8-lts-lgpl

RUN apt update && \
    apt install -y \
    python3-dev python3-distro python3-setuptools \
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
    build-essential \
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
    libssl-dev

ENV QT_ANDROID_ROOT=/opt/Qt-android-5.15.8-lts-lgpl
ENV QT_ANDROID_ROOT_DIR=/opt/Qt-android-5.15.8-lts-lgpl
ENV QMAKE=/opt/Qt-android-5.15.8-lts-lgpl/bin/qmake
ENV OPENSSL_ROOT_DIR=/opt/android_openssl/ssl_1.1
WORKDIR /usr/src

RUN git clone https://gitlab.freedesktop.org/gstreamer/cerbero.git /vendor/cerbero && \
    cd /vendor/cerbero && git checkout 1.22.2 && \
    ./cerbero-uninstalled -c config/cross-android-universal.cbc fetch-bootstrap && \
    ./cerbero-uninstalled -c config/cross-android-universal.cbc fetch-package gstreamer-1.0
RUN cd /vendor/cerbero && ./cerbero-uninstalled -c config/cross-android-universal.cbc bootstrap --offline && \
    QMAKE=/opt/Qt-android-5.15.8-lts-lgpl/bin/qmake ./cerbero-uninstalled -c config/cross-android-universal.cbc -v qt5 package gstreamer-1.0 --offline

ENTRYPOINT [ "" ]