# SimpMusic test builds (unofficial)

<img src="icon.png" width="96" alt="The test build's app icon: a white sound wave, on a bright blue background">

An unofficial test build of [SimpMusic](https://github.com/maxrave-dev/SimpMusic), the YouTube Music
client by maxrave-dev. It is not made or supported by the SimpMusic developers, so please don't report
problems with it to them.

## Download

**[SimpMusic-dev-listen-together-arm64.apk](https://github.com/fhifkldfkljkdf/simplemusic-builds/raw/main/SimpMusic-dev-listen-together-arm64.apk)**
(27.7 MB, for 64-bit Android phones)

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

- **When YouTube limits the app, music keeps playing.** If YouTube starts refusing requests (rate
  limits, "confirm you're not a bot"), the app stops asking YouTube for a while and plays songs from
  the SoundCloud backup straight away, without waiting on YouTube and without a message. A song
  YouTube cuts off midway carries on from the backup where it stopped, after a moment of buffering. YouTube is tried again after 5 minutes (longer if it
  keeps refusing). The backup is 128 kbps MP3, and it only covers songs with a matching full-length
  upload on SoundCloud.

Earlier updates:

- **Hi-Fi sound** (Settings → Playback, off by default). Always plays and downloads the best audio
  YouTube has: 256 kbps with YouTube Premium, about 160 kbps (Opus) without. The sound is left
  untouched while it is on: equalizer, delay, reverb and volume normalisation are bypassed (your
  settings for them are kept). YouTube has no lossless audio, so this is the best quality possible here.
- **SoundCloud as a backup source.** When YouTube won't play a song, the same recording plays from a
  full-length upload on SoundCloud instead of stopping. It only uses an upload whose title, artist and
  length match the song, never a remix, live version or 30-second preview, so songs without such an
  upload still have no backup. Backup audio is 128 kbps MP3, and the song's info sheet says when it is
  playing. Downloads always wait for YouTube. Turn it off in Settings → Content.
- **Moving a song in the queue no longer reshuffles it.** With shuffle on, dragging one song moved it
  and then put every song after the current one in a new random order. Now only the song you moved
  moves.
- **No tracking.** This build has no crash reporting (Sentry) and no Google Play Services (the Cast
  button is gone with it). Sending your listening history to YouTube and uploading lyrics stay off
  unless you turn them on.
- With **High** audio quality and no YouTube Premium, songs could get a video-only stream with no
  sound. They now get the best audio stream instead.
- **Radios play more of the best songs.** Songs that are widely played and well liked now come up sooner,
  and one of the radio's biggest songs comes back at least every few tracks. Obscure uploads (lyric
  re-uploads, off-topic tracks with a few thousand plays) move to the back. A popular artist's biggest
  songs are no longer pushed to the end of the page by the "not too many songs by one artist" rule.
- **Skipping starts sooner.** The next two songs were already loaded ahead of time. Now the app also
  looks up the next five after those, so skipping further ahead or tapping a song further down the
  queue doesn't wait for that step. A song that failed to load ahead of time is tried again.
- **The radio mix slider moved.** It is now the last item in a song's ⋯ menu (under Share), and at the
  bottom of the queue.
- **Brighter, cleaner app icon.**
- **Listen Together finds people on the same Wi-Fi by itself**: type the code and you connect straight to
  the host's phone, and rooms nearby show up to join with one tap.
- **The radio mix is a slider**, from Familiar to New.
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
[SimpMusic-source-58dad80.zip](SimpMusic-source-58dad80.zip) is the complete source code this build was
made from, including the changes above: the app at commit `58dad80` and its `core` module at `9eb8e25`.
Build it with `./gradlew :androidApp:assembleOptimized` (an unsigned release-type APK, to sign with
your own key) or `./gradlew :androidApp:assembleDebug` (Android SDK and JDK 21 required).
