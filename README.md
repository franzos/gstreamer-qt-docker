# GStreamer with QT on Docker

This is a Docker image for building Android applications on CI services specifically for those that require GSteamer and QT. The Dockerfile inherits https://github.com/carlonluca/docker-qt and will save your hours building this from scatch but the image is quite large - so if your connection is slow, you're better off building this locally.

## Releases


- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.20.6-android-latest`
- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.20.6-android-v0.2`
- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.20.6-android-v0.1` - First version of the image (`v0.1`)
  - Qt `5.15.8-lts`
  - GStreamer `1.20.6` with Qt (cross-android-universal)
- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.22.2-android-latest`
- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.22.2-android-v0.2`
- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.22.2-android-v0.1` - First version of the image (`v0.1`)
  - Qt `5.15.8-lts`
  - GStreamer `1.22.2` with Qt (cross-android-universal)
- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.22.5-android-latest`
- `franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.22.5-android-v0.1` - First version of the image (`v0.1`)
  - Qt `5.15.8-lts`
  - GStreamer `1.22.5` with Qt (cross-android-universal)

GStreamer was compiled with the following plugins:

```
./cerbero-uninstalled -c config/cross-android-universal.cbc -v qt5 package gstreamer-1.0
```

### All releases

| Type                               | Releases |    |    |
|------------------------------------|----------|----|----|
| 5.15.8-lts-lgpl-gst-1.20.6-android | latest   | v1 | v2 |
| 5.15.8-lts-lgpl-gst-1.22.2-android | latest   | v1 | v2 |
| 5.15.8-lts-lgpl-gst-1.22.5-android | latest   | v1 |    |
|                                    |          |    |    |

## Usage

For ease, add a `docker-compose.yml` to your project:

```yaml
version: '3.6'

services:
  builder:
    image: franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.20.6-android-v0.1
    command: tail -f /dev/null
    environment:
      - QT_GRAPHICSSYSTEM=native
    volumes:
      - .:/usr/src
      - /tmp/.X11-unix:/tmp/.X11-unix
```

Start the container and connect to it.

```bash
docker compose -up
docker exec -it qt-gst-builder bash
```

If you prefer to run the container in the background, do `docker compose -up -d`.

## TODO

- [ ] Support newer Android SDK's
- [ ] Support different GStreamer versions

## Release

```bash
docker build -t qt-gst-builder .
docker tag qt-gst-builder franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.20.6-android-v0.1
docker push franzos/gstreamer-qt:5.15.8-lts-lgpl-gst-1.20.6-android-v0.1
```

On Linux hosts without iptables:

```bash
docker build --network=host -t qt-gst-builder .
```