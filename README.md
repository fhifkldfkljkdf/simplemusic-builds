# SimpMusic test builds (unofficial)

<img src="icon.png" width="96" alt="The test build's app icon: five white rounded bars of a sound wave, on a blue background">

An unofficial test build of [SimpMusic](https://github.com/maxrave-dev/SimpMusic), the YouTube Music
client by maxrave-dev. It is not made or supported by the SimpMusic developers, so please don't report
problems with it to them.

## Download

**[SimpMusic-dev-listen-together-arm64.apk](https://github.com/fhifkldfkljkdf/simplemusic-builds/raw/main/SimpMusic-dev-listen-together-arm64.apk)**
(29.3 MB, for 64-bit Android phones)

1. Open the link on your phone. No GitHub account is needed.
2. Open the downloaded file. The first time, Android asks you to allow installing apps from your browser.
3. Tap **Install**.

It installs as a separate app next to SimpMusic (package `com.maxrave.simpmusic.dev`), so your
normal SimpMusic is left alone. It has its own icon (above), so you can tell the two apart. If you installed an earlier test build from here, this one installs
over it and keeps your data.

This is an optimized build: the same code a release is built from (shrunk, without debug checks), so
it is smaller and runs faster than the earlier test builds, which were debug builds. It is signed with
a throwaway test key, not the SimpMusic developers' key.

## What is different in this build

New in this update:

- **Listen Together finds people on the same Wi-Fi by itself.** Phones on the same network now find
  each other automatically: type the room code and you connect straight to the host's phone, with no
  QR code to scan and no internet needed. Rooms hosted on your Wi-Fi also show up under **Nearby on this
  Wi-Fi** on the Listen Together page, to join with one tap (the host still lets you in). Hosts who
  don't want to be listed can turn off **Show my rooms on this Wi-Fi** in Listen Together settings.
  If the host's phone leaves, the next person takes over and everyone else finds them automatically.
- **The radio mix is now a slider.** In a song's menu under **Start radio**, at the top of a radio's
  queue, and in Settings: drag from **Familiar** (songs and artists you know) to **New** (songs you
  haven't heard), with the current choice named above it ("Mostly new", "Mix"…).
- **Blue app icon.**

Earlier updates:

- **Listen Together connects phones directly on the same Wi-Fi**, beside the relays, so a room keeps
  playing when the relays are slow or unreachable. The room screen shows how you are connected.
- **Start radio plays songs you have not heard** (with the mix on New), and keeps doing so as it goes on.
- **Radios stop repeating themselves.** Repeats of the same song (official video, audio, lyric video)
  are left out, no artist gets more than 2 songs in any 8, and when too few new songs are left the
  radio branches out from new songs it found.
- **Listen Together recovers from lost messages**, and catches up with the host by itself after a
  dropped connection.
- **Playback keeps going.** When the connection drops, the song waits for it and carries on where it
  stopped. A song that will not play is skipped (with a short message) instead of stopping the queue.

Listen Together:

- **Peer to peer, with no server.** The host's phone runs the room, and everyone else reaches it
  directly on the same Wi-Fi and through public Nostr relays, end-to-end encrypted with the room code. If the host leaves, or their phone
  goes quiet (app closed, no signal), the next person in the room takes over after about 30 seconds and
  the music carries on. Everyone in a room needs this build: rooms no longer work with the official
  SimpMusic or Metrolist.
- You stay in a room when your connection drops, for up to 15 minutes, and rejoin by yourself.
- **Listen on my own**: play other songs without leaving the room, then come back with one tap.
- **Share what I play**: while listening on your own, the host sees your songs as suggestions and can
  play them for everyone.
- **Room QR codes**: tap the QR button next to the room code to show it. Friends join by tapping
  **Scan QR code** in Listen Together, or by scanning it with their phone's camera app. Your name is
  remembered, so joining by QR code needs no typing.

Friends:

- Open **Friends** from Listen Together. Show your friend code, or add a friend by scanning theirs
  (**Scan friend code**) or pasting their link. One of you adding the other is enough: the other gets
  a request to accept.
- In a room, tap **Invite friends**, then **Invite** next to a friend. They get a pop-up wherever they
  are in the app and join with one tap (the host still lets them in).
- No account and no server: messages travel through public Nostr relays, end-to-end encrypted, so the
  relays cannot read names or room codes. Invites only arrive while SimpMusic is running.

Radio:

- Radios learn from what you listen to on this phone: songs you just heard are held back, songs you
  usually skip come later, and artists you play a lot come sooner. Turn it off in Settings
  (**Learn from my listening in radio**). It needs local tracking on.
- **Familiar or new songs**: the radio mix slider under Start radio, in a radio's queue, and in
  Settings. Left gives more songs and artists you already know, right gives more you have never heard.
- **Start radio** on the song that is playing keeps it playing, instead of starting it over.

Playback:

- Songs no longer get stuck at the end of a track: a next song that failed to preload is loaded again,
  a stream that stalls just before its end moves on, and a radio page that arrives late still plays.

## Source code

SimpMusic is licensed under the GNU General Public License v3.0 (see [LICENSE](LICENSE)).
[SimpMusic-source-ac12c2d.zip](SimpMusic-source-ac12c2d.zip) is the complete source code this build was
made from, including the changes above: the app at commit `ac12c2d` and its `core` module at `9ba63cf`.
Build it with `./gradlew :androidApp:assembleOptimized` (an unsigned release-type APK, to sign with
your own key) or `./gradlew :androidApp:assembleDebug` (Android SDK and JDK 21 required).
