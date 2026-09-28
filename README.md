# SimpMusic test builds (unofficial)

An unofficial test build of [SimpMusic](https://github.com/maxrave-dev/SimpMusic), the YouTube Music
client by maxrave-dev. It is not made or supported by the SimpMusic developers, so please don't report
problems with it to them.

## Download

**[SimpMusic-dev-listen-together-arm64.apk](https://github.com/fhifkldfkljkdf/simplemusic-builds/raw/main/SimpMusic-dev-listen-together-arm64.apk)**
(66.5 MB, for 64-bit Android phones)

1. Open the link on your phone. No GitHub account is needed.
2. Open the downloaded file. The first time, Android asks you to allow installing apps from your browser.
3. Tap **Install**.

It installs as a separate app next to SimpMusic (package `com.maxrave.simpmusic.dev`), so your
normal SimpMusic is left alone. It is a debug build signed with a throwaway key.

## What is different in this build

Listen Together:

- You stay in a room when your connection drops, for up to 15 minutes, and rejoin by yourself.
- **Listen on my own**: play other songs without leaving the room, then come back with one tap.
- **Share what I play**: while listening on your own, the host sees your songs as suggestions and can
  play them for everyone.

## Source code

SimpMusic is licensed under the GNU General Public License v3.0 (see [LICENSE](LICENSE)).
[SimpMusic-source-5dabf3d.zip](SimpMusic-source-5dabf3d.zip) is the complete source code this build was
made from, including the changes above: the app at commit `5dabf3d` and its `core` module at `6f16a72`.
Build it with `./gradlew :androidApp:assembleDebug` (Android SDK and JDK 21 required).
