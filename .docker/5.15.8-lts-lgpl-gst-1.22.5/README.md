I had issues with some binaries so I had to include them manually.

```bash
77.94 Running command ['wget', '--user-agent', 'GStreamerCerbero/1.22.5', '--tries=2', '--timeout=20', '--progress=dot:giga', '-O', '/root/.cache/cerbero-sources/proxy-libintl-0.1/0.1.tar.gz', 'https://github.com/frida/proxy-libintl/archive/0.1.tar.gz'] in .
77.94 --2023-08-28 18:15:40--  https://github.com/frida/proxy-libintl/archive/0.1.tar.gz
77.94 Resolving github.com (github.com)... 140.82.121.3
77.94 Connecting to github.com (github.com)|140.82.121.3|:443... connected.
77.94 HTTP request sent, awaiting response... 302 Found
77.94 Location: https://codeload.github.com/frida/proxy-libintl/tar.gz/refs/tags/0.1 [following]
77.94 --2023-08-28 18:15:40--  https://codeload.github.com/frida/proxy-libintl/tar.gz/refs/tags/0.1
77.94 Resolving codeload.github.com (codeload.github.com)... 140.82.121.10
77.94 Connecting to codeload.github.com (codeload.github.com)|140.82.121.10|:443... connected.
77.94 HTTP request sent, awaiting response... 403 Forbidden
77.94 2023-08-28 18:15:40 ERROR 403: Forbidden.
77.94 
77.94 Running command ['wget', '--user-agent', 'GStreamerCerbero/1.22.5', '--tries=2', '--timeout=20', '--progress=dot:giga', '-O', '/root/.cache/cerbero-sources/proxy-libintl-0.1/0.1.tar.gz', 'https://gstreamer.freedesktop.org/src/mirror/0.1.tar.gz'] in .
77.94 --2023-08-28 18:15:40--  https://gstreamer.freedesktop.org/src/mirror/0.1.tar.gz
77.94 Resolving gstreamer.freedesktop.org (gstreamer.freedesktop.org)... 131.252.210.176, 2610:10:20:722:a800:ff:feda:470f
77.94 Connecting to gstreamer.freedesktop.org (gstreamer.freedesktop.org)|131.252.210.176|:443... connected.
77.94 HTTP request sent, awaiting response... 404 Not Found
77.94 2023-08-28 18:15:41 ERROR 404: Not Found.
77.94 
77.94 Running command ['wget', '--user-agent', 'GStreamerCerbero/1.22.5', '--tries=2', '--timeout=20', '--progress=dot:giga', '-O', '/root/.cache/cerbero-sources/props://gstreamer.freedesktop.org/src/mirror/0.1.tar.gz'] in .
77.94 --2023-08-28 18:15:41--  https://gstreamer.freedesktop.org/src/mirror/0.1.tar.gz
77.94 Resolving gstreamer.freedesktop.org (gstreamer.freedesktop.org)... 131.252.210.176, 2610:10:20:722:a800:ff:feda:470f
77.94 Connecting to gstreamer.freedesktop.org (gstreamer.freedesktop.org)|131.252.210.176|:443... connected.
77.94 HTTP request sent, awaiting response... 404 Not Found
77.94 2023-08-28 18:15:41 ERROR 404: Not Found.
```