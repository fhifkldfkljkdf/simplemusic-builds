# SimpMusic test builds (unofficial)

<img src="icon.png" width="96" alt="The test build's app icon: a white play button cut through by a sound wave, on a blue-to-violet background">

An unofficial test build of [SimpMusic](https://github.com/maxrave-dev/SimpMusic), the YouTube Music
client by maxrave-dev. It is not made or supported by the SimpMusic developers, so please don't report
problems with it to them.

## Download

**[SimpMusic-dev-listen-together-arm64.apk](https://github.com/fhifkldfkljkdf/simplemusic-builds/raw/main/SimpMusic-dev-listen-together-arm64.apk)**
(28.1 MB, for 64-bit Android phones)

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

- **New app icon.** A white play button cut through by a sound wave, on a blue-to-violet background.
  The same mark now replaces the old SimpMusic note everywhere it was still showing: the status bar
  and media controls, Android Auto, the logo inside the app, and the Credits screen.
- **Songs start sooner.** For a song that isn't cached yet, the app now asks YouTube for the song's
  details and the playable stream at the same time instead of one after the other, and skips a
  duplicate check of the stream address. The code that unlocks YouTube's streams is prepared
  just after the app opens, so the first song no longer waits for it. With Hi-Fi sound on, a tapped
  song whose lossless file is already known starts right away on YouTube and moves to the lossless
  file a little later, instead of waiting about a second for archive.org; songs coming up in the queue
  still load the lossless file in advance. Upcoming songs are also looked up while the app waits for
  their lossless search, so skipping ahead stays instant.
- **The move to lossless is meant to go unnoticed.** If the lossless copy is louder, it stays at the
  level you were hearing until the song ends instead of being turned up; if it is quieter, the song
  is brought down to it very slowly before the switch. A song whose lossless copy can't be lined up
  without a seam starts on that copy the next time instead.
- **Noise control holds its connection better.** MOMENTUM 4: a slow battery answer, or a setting the
  firmware doesn't report, no longer stops noise control from appearing. Closing and reopening the
  player no longer reconnects to the headphones, and a change made right after connecting is no
  longer lost.
- **Up to date with SimpMusic 2.3.0.** The latest official changes are merged in, including its bug
  fixes (shuffled queue order kept when songs are added, playlist edits past the first page,
  Japanese lyrics romanization after a reinstall, seek bars while paused) and its redesigns of the
  Apple Music-style player, Settings and Home. The new launch banners on Home are left out, like the
  other pop-ups.
- **Fixed:** automatic backups didn't work on Android 8 and 9.

Earlier updates:

- **No more pop-ups from the developer.** Upstream SimpMusic asks, at set numbers of app opens, for a
  GitHub star or review, to share your saved lyrics, to read the developer's blog, and to star the developer's
  "kotlin-footguns" project. All of those are gone, and so is the "log in to YouTube" warning. The
  daily job that checked the developer's blog and sent you notifications about new posts is removed,
  together with its Settings switch, and old blog notifications no longer appear. The app also
  stopped checking for official SimpMusic releases every time it starts (those are a different app
  from this build); **Check for update** in Settings still works if you ask.
- **Fixes.** Some failures in the background (a lossless or SoundCloud search, switching sources,
  the headphone connection) could close the whole app; now they're logged and the app carries on.
  Seeking used to stop a song from switching to its lossless copy for the rest of the song; it now
  tries again from where you seeked to.

- **Noise cancelling for Huawei and Honor earbuds.** The same label and panel as the MOMENTUM 4 now
  work with Huawei FreeBuds (including the FreeBuds Pro 4 and FreeBuds 6i), FreeClip, FreeLace and
  Honor Earbuds. Depending on the model you can switch between noise cancelling, awareness
  (transparency) and off, pick the cancelling level (Comfort, Normal, Ultra, Dynamic) and voice
  boost, and see the battery of each earbud and the case. Earbuds without noise control show their
  battery. The model list and protocol come from [OpenFreebuds](https://github.com/melianmiko/OpenFreebuds);
  models it doesn't list are recognised by name and may only partly work. The first time, tap the
  label and then **Allow** (the "Nearby devices" permission). If it can't reach the earbuds, close
  HUAWEI AI Life and tap **Try again**. Like the MOMENTUM 4 support, this has not been tried on real
  earbuds yet.

- **Noise cancelling for Sennheiser MOMENTUM 4.** When your MOMENTUM 4 is connected, the player shows
  its noise cancelling next to the source label under the seek bar: "ANC 80%", "Adaptive ANC",
  "Transparency" or "ANC off". Tap it to switch between ANC, Adaptive, Transparent and Off, set how
  strongly ANC cancels with a slider, choose wind noise reduction (Off, Maximum, Automatic), and see the
  battery. Changes you make on the headphones themselves show up right away.
  The first time, tap the label and then **Allow**: Android asks for the "Nearby devices" permission,
  which the app needs to talk to the headphones. If it says it can't reach them, close Sennheiser
  Smart Control and tap **Try again**.
  This is built from how other people decoded the headphones' control protocol, not from anything
  Sennheiser published, and it has not been tried on a real MOMENTUM 4 yet.

- **Fixed: some Internet Archive songs played with no sound.** The player fetches a song in pieces,
  and a later piece could come from YouTube's copy instead of the FLAC file, which the player cannot
  read. Each song now stays on the file it started with. Archive files are also checked before use
  (a real FLAC file, stereo, the right length, downloadable), and CD-quality files are preferred.
  Files above 96 kHz are skipped: the phone plays them at 48 kHz anyway, and they stutter on slow
  connections.
- **Songs start right away.** With Hi-Fi sound on, a song used to wait up to 6 seconds while the
  Internet Archive was searched. Now it starts at once from the fastest source, and the search runs
  in the background. Songs coming up in the queue are looked up ahead of time, so they start in
  lossless straight away.
- **Quality upgrades by itself, without a break.** When the lossless file for the song that is playing
  turns up, the app opens it silently, lines it up with what you hear to within about a millisecond,
  matches the volume, and switches over. If the two copies don't line up exactly (different
  remasters often don't), it doesn't switch mid-song, and the next time the song plays it starts in
  lossless.
- **See every source.** Tap the source label under the seek bar to see where the song can play from:
  Internet Archive (lossless), YouTube and SoundCloud, each with its quality, and which one is playing.
  Tap another to switch to it. This uses the seamless switch when it can, otherwise the song reloads
  where it is.


- **Lossless (FLAC) with Hi-Fi sound, no account needed.** With Hi-Fi sound on (Settings → Playback),
  songs play from a FLAC file on the Internet Archive (archive.org) when it has the same recording
  (title, artist and length match, not a live, demo or remixed version), otherwise from YouTube.
  Many songs are there, many are not: Queen's "Bohemian Rhapsody" is, Taylor Swift's "Shake It Off"
  is not. Lossless files are large (about 10 times YouTube's size), so this uses a lot more data on
  mobile.
- **New app icon.** A play button sending out two sound waves: music that plays and reaches the
  people listening with you.
- **The player shows where the music comes from.** A small label under the seek bar reads, for
  example, "YouTube · OPUS 160 kbps", "SoundCloud · MP3 128 kbps" or "Downloaded". It changes if a
  song switches to the backup midway.
- **More songs are ready ahead of time.** The next three songs are fully loaded (was two), the next
  ten are looked up (was five), and the opening minute or so of five more is saved, so skipping
  further ahead starts straight away. This uses up to about 8 MB of extra data ahead of time.
- **Less is sent about what you play:**
  - The like/dislike counter service (Return YouTube Dislike) is no longer asked about every song.
  - SponsorBlock, when you turn it on, no longer learns which video you play: it is asked about a
    group of videos and the app picks out the right one.
  - The BPM/key lookup on TIDAL for every song now only runs while DJ crossfade is on.
  - Reporting what you play to YouTube and uploading lyrics to SimpMusic are removed from Settings
    and always off.
- **Latest SimpMusic changes included** (from the original app's core), among them playback of
  YouTube live broadcasts.
- **When YouTube limits the app, music keeps playing.** If YouTube starts refusing requests (rate
  limits, "confirm you're not a bot"), the app stops asking YouTube for a while and plays songs from
  the SoundCloud backup straight away, without waiting on YouTube and without a message. A song
  YouTube cuts off midway carries on from the backup where it stopped, after a moment of buffering. YouTube is tried again after 5 minutes (longer if it
  keeps refusing). The backup is 128 kbps MP3, and it only covers songs with a matching full-length
  upload on SoundCloud.
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
[SimpMusic-source-109ba83.zip](SimpMusic-source-109ba83.zip) is the complete source code this build was
made from, including the changes above: the app at commit `109ba83` and its `core` module at `1bd39bd`.
Build it with `./gradlew :androidApp:assembleOptimized` (an unsigned release-type APK, to sign with
your own key) or `./gradlew :androidApp:assembleDebug` (Android SDK and JDK 21 required).
