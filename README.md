# SimpMusic test builds (unofficial)

An unofficial test build of [SimpMusic](https://github.com/maxrave-dev/SimpMusic), the YouTube Music
client by maxrave-dev. It is not made or supported by the SimpMusic developers, so please don't report
problems with it to them.

## Download

**[SimpMusic-dev-listen-together-arm64.apk](https://github.com/fhifkldfkljkdf/simplemusic-builds/raw/main/SimpMusic-dev-listen-together-arm64.apk)**
(66.7 MB, for 64-bit Android phones)

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
- **Room QR codes**: tap the QR button next to the room code to show it. Friends join by tapping
  **Scan QR code** in Listen Together, or by scanning it with their phone's camera app. Your name is
  remembered, so joining by QR code needs no typing.

Friends (new):

- Open **Friends** from Listen Together. Show your friend code, or add a friend by scanning theirs
  (**Scan friend code**) or pasting their link. One of you adding the other is enough: the other gets
  a request to accept.
- In a room, tap **Invite friends**, then **Invite** next to a friend. They get a pop-up wherever they
  are in the app and join with one tap (the host still lets them in).
- Peer to peer: there is no account and no server for this. Messages travel through public Nostr
  relays, end-to-end encrypted, so the relays cannot read names or room codes. Invites only arrive
  while SimpMusic is running.

Radio:

- Radios learn from what you listen to on this phone: songs you just heard are held back, songs you
  usually skip come later, and artists you play a lot come sooner. Turn it off in Settings
  (**Learn from my listening in radio**). It needs local tracking on.

## Source code

SimpMusic is licensed under the GNU General Public License v3.0 (see [LICENSE](LICENSE)).
[SimpMusic-source-8d84dc9.zip](SimpMusic-source-8d84dc9.zip) is the complete source code this build was
made from, including the changes above: the app at commit `8d84dc9` and its `core` module at `f11db86`.
Build it with `./gradlew :androidApp:assembleDebug` (Android SDK and JDK 21 required).
