# SimpMusic test builds (unofficial)

<img src="icon.png" width="96" alt="The test build's app icon: a pixel-art white sound wave on a black background">

An unofficial test build of [SimpMusic](https://github.com/maxrave-dev/SimpMusic), the YouTube Music
client by maxrave-dev. It is not made or supported by the SimpMusic developers, so please don't report
problems with it to them.

## Download

**[SimpMusic-dev-listen-together-arm64.apk](https://github.com/fhifkldfkljkdf/simplemusic-builds/raw/main/SimpMusic-dev-listen-together-arm64.apk)**
(28.2 MB, for 64-bit Android phones)

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

- **Retro Pixel is now a full pixel/ASCII pass.** Icons are sampled into a chunky 12×12 pixel grid, the whole
  app's text uses the bundled VT323 terminal face, and faint CRT scanlines sit over the screen — on top of the
  square corners and 8-bit palette. It covers the navigation bar, top bars, player, mini player, Home cards and
  Settings.
- **Themes now change more than colour.** Each theme carries its own corners (Apple's softer cards, Ocean's
  glassy radii, AMOLED/Retro's sharp edges), filter-pill style, navigation capsule/indicator shape and typeface
  (system sans for Apple/Ocean/AMOLED, monospace for Retro). Home gets a signature touch per theme — Apple Music's
  "Top Picks" editorial row, Ocean's tinted header, flat headers for AMOLED/Retro, Spotify's quick grid — and
  choosing Spotify or Apple Music also switches the player layout to match. Named themes also paint the desktop
  window's surfaces.
- **A theme picker with more themes.** Settings → **App theme** now opens a visual swatch grid: Default,
  Material You, Spotify, Apple Music, Ocean, AMOLED Black, **Retro Pixel** and Custom. Every theme has a light
  and a dark variant and follows the existing light/dark/system setting; the selected one is ticked.
- **Retro Pixel** is an 8-bit theme: neon green, magenta and cyan on a near-black (or paper-light) background,
  blocky corners and monospace text throughout.
- **A Spotify theme.** Choose **Spotify**: the app takes Spotify's palette (dark #121212 surfaces with #1DB954
  green, or a white light variant) and Home takes its shape — a greeting-only header, filled filter pills instead
  of outlined ones, and a two-column quick-access grid of your most-played songs at the top. The current tile and
  the hearts turn green, and the Spotify player layout uses the same palette.
- **Playback speed now goes up to 3×.** The speed control's + button used to stop at 2×; it now steps to 3×, for
  songs and podcasts alike.
- **Genre rows only follow artists you actually play.** R&B and dance rows used to count every artist you had ever
  heard, so one random play could fill a whole row; they now count only artists from your most-played songs and
  start from the one you play most in that genre.
- **Top artists is now near the top of Home**, right after the first row, as big circular cards — it no longer
  lives in the Charts block at the bottom.
- **The Charts block is trimmed.** YouTube's "Video charts" row and the country selector are gone, and the whole
  block disappears when it has no row left to show.
- **Recommendations no longer include alternate versions.** Covers, karaoke, instrumentals, remixes, live takes,
  sped-up/slowed/nightcore/8D, acoustic and AI versions are filtered out of Quick picks, New for you, Because you
  played, More like and the genre rows. Listen again keeps your own songs as they are.
- **Genre rows are built from your artists.** Each "<Genre> for you" row plays a radio from a song by one of your
  own artists in that genre, starting with the one you play most, instead of the genre page's random top songs.
- **Top artists is now a shelf of big circular cards.** Your most played artists lead — drawn from every play,
  not just the last fifty songs — with the name underneath and no rank numbers; genuinely new artists say
  "New to you", and related artists you have heard before say "You might like".
- **The new Home rows each have their own look.** "Because you played <song>" opens with a full-width feature
  card of that song (title and artists over the art, with a play button) above the radio's songs; "More like
  <artist>" is a row of wide 16:9 cards; and "<Genre> for you" is a compact numbered Top 5 list. Quick picks, New
  for you, Listen again, Recommended genres and Top artists keep their existing looks.
- **Home's rows are now made for you, not by YouTube.** Quick picks, New for you and Listen again are joined by
  "Because you played <song>", up to three "More like <artist>" rows, "Recommended genres" and "<Genre> for you"
  rows, all built from what this phone plays (signed in or out). YouTube's own feed shelves now show only when
  there is no listening history to build from, and every row leaves out songs already shown above it.
- **The duplicate "Quick picks" is gone.** YouTube's own Quick picks row used to sit under the app's one, looking
  the same; YouTube's rows are dropped whenever the app's own rows exist.
- **Home's "Top artists" is now your artists, with new ones to try.** The grid under Charts leads with the artists
  this phone plays most, then with artists related to them that you have not heard yet — each of those marked
  "New to you" — instead of YouTube's same-for-everyone chart.
- **A "Recommended genres" row now appears in the Home feed.** The app checks YouTube's genre pages against the
  artists you have heard and the songs you play most, and shows the genres that fit, as the same stripe cards the
  Moods & genres grid uses. Both work signed in or out, and both are cached, so they cost nothing on later opens.
- **Home's "Take it easy" row is now a "For you" row built from what you listen to.** The Home feed's own
  "Take it easy" shelf is removed and replaced in its place by songs picked from radios of the tracks this phone
  plays most — never-heard songs first, then songs worth hearing again — signed in or out.
- **A headphone's name reads cleanly, and the noise-control sheet scrolls it calmly.** The maker's prefix is
  dropped ("HUAWEI FreeBuds 6i" reads "FreeBuds 6i"), and a device alias or a tag the phone added is never shown
  in the sheet, the pill or the permission notice; the sheet's marquee now moves at a readable speed with a pause
  between passes.
- **A headphone's name too long for the noise-control sheet now scrolls.** The sheet's header used to cut the
  name off with an ellipsis; it moves now, so the whole name can be read, with the battery still beside it.
- **"Download songs you like" now downloads all of them, and finishes even if you leave Settings.** The catch-up
  used to run inside the settings screen: leaving it stopped the sweep half-way, so only the first few favourites
  were queued. It now runs in the background and queues three at a time, and it treats a song as downloaded only
  when the copy on the phone is whole — the partial file of a download that failed used to make it skip that song.
  If some still cannot be downloaded, a toast says how many, and switching the option off and on again tries them.
- **The "Download songs you like" catch-up says how far it has got.** Switching it on still queues every favourite
  that is not on the phone; the switch's row now reads "Downloading 4 of 12 liked songs…" until the last one lands,
  and the toast still names how many were queued.
- **The sources sheet opens for a downloaded song.** Tapping the source pill right after a downloaded song started
  showed no sheet at all — the sheet waited for the player to match its media item back to a queue row, which for a
  downloaded song had not happened yet — and it appeared only once the next song started. It now works from the
  song's own id and opens at once; if its list of sources is ever slow to arrive it asks again instead of spinning.
- **Downloads from other sources are checked to be the right song.** Monochrome was serving another recording
  under some songs' names: for Pixies' "Where Is My Mind?" it handed out a 3:11 cover by another artist, so the
  download (and Hi-Fi playback) was not the song. Every file from Monochrome or the Internet Archive is now checked
  against the song by its real length, its ISRC and its own artist and title tags, before it is played or kept.
  Earlier matches are looked up again, and downloads already on your phone that turn out to be another recording are
  replaced with YouTube's copy at start-up.
- **Downloaded songs say what they really are.** The player read the format of YouTube's stream for every downloaded
  song, so a FLAC said "OPUS". It now reads the file itself: "Downloaded · FLAC 24/44.1", or "Downloaded · OPUS 134
  kbps" for a YouTube copy. The number shown beside it was the speed of reading the file from the phone, not a
  download; it no longer appears for downloaded songs.
- **Picking a source in the sheet works for downloaded songs.** Choosing YouTube for a song downloaded from another
  source now really plays YouTube's stream (it played the download again), and the downloaded copy stays in the list
  so you can switch back to it.
- **A plain download no longer takes SoundCloud.** When no lossless or Audius copy answers, a download now takes
  YouTube's own stream instead of a SoundCloud re-upload, which was 128 kbps MP3 (below YouTube's quality) and the
  likeliest to be another version of the song. SoundCloud can still be picked by hand in the sources sheet.
- **Songs downloaded from other sources play to the end.** A song downloaded from Monochrome, the Internet Archive,
  Audius or SoundCloud played its first seconds (about 25 s of a hi-res FLAC) and then went quiet. The file itself was
  whole; the player read downloaded songs in 5 MB pieces, which works for YouTube's own files but makes a FLAC or MP3
  end at the first piece. Downloads from those sources are now read in one go and play to their last second, songs
  downloaded earlier included. A download also stays on one file when the connection drops and it resumes, never
  fills the rest with YouTube's audio, and is kept only when it matches the source's file exactly.
- **The download button shows a circle with the percentage.** While a song downloads, the Download row in the song
  menu shows a ring that fills up with the percentage inside. The sources sheet shows the same ring on the row of the
  source being downloaded.
- **Noise control keeps its place next to the heart in the phone's media controls.** The notification, lock screen
  and quick-settings player show two buttons beside play: the heart, then noise control. Noise control used to
  appear only once the app was talking to the headphones, so until then (most often because the Bluetooth
  permission had never been granted) Shuffle took its place. The button is now there whenever supported headphones
  are connected: "Allow ANC control" (tap it, then the notice it posts, and grant the permission), "ANC ·
  connecting", or "ANC · tap to retry". Shuffle shows only without supported headphones, or with earbuds that have
  no noise control.
- **The finished-download notification has its own switch, in Android's notification settings.** The notice
  ("Song · 24.6 MB · from Monochrome") goes out on a channel of its own, listed as "Download complete" in Android's
  app notification settings, so it can be turned off there without muting the progress notification — and that is
  the only place the switch lives: there is deliberately no copy of it inside the app.
- **A copy from a better source has to open like an audio file before it replaces anything.** Beside the size rule,
  the first bytes of the fetched copy are checked (FLAC, Ogg, MP3, AAC, M4A, WebM); anything else — an error page, a
  playlist, a redirect stub — is treated as a broken copy and never becomes the song's, so a download can no longer
  leave a copy with no sound in it.
- **The copies that lost their sound are found more reliably.** The check after start-up looks at the opening bytes
  as well as the size, so a copy from the first source-download attempt that has no audio in it at all is fetched
  again from YouTube's whole stream, not only the ones that came out short.
- **The short-copy check no longer asks the sources about every source copy at every launch.** A copy that was
  verified when it arrived carries the size it was checked against, so the pass that runs after start-up trusts it;
  only copies from earlier builds cost a request.
- **Upgrading a download now really downloads it.** A song already on the phone was never re-fetched: Media3
  answered the new download entirely from the copy it already had, so "Upgrade downloads" and the sources sheet's
  per-song download could finish instantly without touching the source — the copy stayed as it was. A source's copy
  is now fetched into a staging area beside the old one, measured against the size the source declared, and only a
  whole copy replaces it; a short or failed one leaves the old copy as it is, and a first download with nothing to
  fall back on takes YouTube's whole stream instead.
- **A plain download is quality-first.** The ordinary Download button — song, album, playlist, "Download songs you
  like" — now asks the sources first and takes the best copy that answers: Monochrome's or the Internet Archive's
  FLAC, Audius' upload, or the SoundCloud backup, and YouTube's stream when none does. It does this on Wi-Fi and
  other unmetered connections only; on mobile data a plain download takes YouTube as before, and the Settings
  upgrade dialog is still where you choose to spend data on an upgrade. The source switches (Hi-Fi sound, each
  source) still gate it, and a source button in the sources sheet still takes exactly that source.
- **The finished-download notification says what arrived:** "Song · 24.6 MB · from Monochrome", and for an upgrade
  only once its copy has been checked. A fetch that failed and kept the old copy no longer posts a failure notice.
- **Short copies are actually repaired now.** The repair pass the last build announced looked in the list of
  *active* downloads, so a finished (short) copy was never examined; it now reads the download records, so the
  copies the first source-download attempt left behind are measured and taken again from YouTube.
- **A download from another source is taken only when the answer really is the song - YouTube's own downloads are
  untouched.** The length rule now also requires the source to declare at least 64 kB: a playlist (SoundCloud's
  HLS answers), an error page or a redirect stub declares a few kilobytes, and downloading that would have left
  another copy with no sound. Anything under it is skipped and YouTube's whole stream is fetched instead, so a
  download is either the whole song from the source or YouTube's file.
- **"Download songs you like" now downloads the ones that are not on the phone.** Its sweep used to trust each
  song's row, and that flag outlives a copy - a download removed by hand, never finished, or left short by the
  first source-download attempt still read "downloaded", so switching the option on skipped exactly the favourites
  it was asked for. It now asks the download cache itself, and queues whatever is missing; switching it on is the
  catch-up, however many times you switch it.
- **The downloads that lost their sound come back by themselves.** Songs an earlier build downloaded from a
  better source could be left short - playing their opening and then nothing. About twenty seconds after the app
  opens, each such copy is measured against the size its source declares and, if it does not measure up, downloaded
  again from YouTube's whole stream. Nothing to tap: it settles in one pass and touches only those copies.
- **Upgrading over mobile data is allowed, and asked for.** Settings' "Upgrade downloads" on a metered
  connection says what it will cost in data and its **Upgrade** now really runs there - the flag reaches the work
  (2.4.34 announced this and did not carry it; this build does).
- **Ask on mobile (words only).** The dialog text for the metered question landed here; the behaviour itself
  arrived in 2.4.35.
- **No user-visible change** (the strings for the next build; the metered question itself arrived in 2.4.34).
- **Downloads from Monochrome, the Internet Archive, Audius and SoundCloud are back.** But only from a source
  that **declares how big its file is** - that length is what makes a streamer answering with part of a song
  *fail* the download rather than "complete" it, which is how the last attempt left copies that played only their
  start. A source that will not say is skipped for YouTube's stream. The old copy stays on the phone until the new
  download completes, so a failed upgrade cannot leave a song without one; the sources sheet's per-song download
  and Settings' "Upgrade downloads" come back with it.
- **Downloads are YouTube's again, for now.** Downloading a song from Monochrome, the Internet Archive,
  Audius or SoundCloud is switched off in this build: the last one could leave a copy that played only its start,
  because those files are not always a whole, plain stream - a FLAC's audio can begin after a large metadata block,
  and a streamer can answer with less than the file - and nothing checked the copy before it replaced the old one.
  The per-song download button in the sources sheet (except YouTube's) and Settings' "Upgrade downloads" are gone
  until a copy can be verified and the audio offset honoured. A song that was upgraded badly is fixed by tapping
  **Downloaded** in its sheet (which removes the copy) and then **Download** again.
- **Upgrade every download from Settings.** In Settings → Storage, beside the downloaded cache: each downloaded
  song is looked up on the better sources and, when one has it, fetched again and the copy on the phone replaced —
  Monochrome's FLAC instead of YouTube's stream, for the whole library in one tap. Songs with nothing better are
  left exactly as they are, and it waits for Wi-Fi rather than spending a metered plan. The row reads
  "Upgrading 3 of 12…" while it runs.
- **The download notification says what is happening.** While songs download it now reads "Song · 45% · 12.4 MB ·
  1.2 MB/s · from Monochrome" — how far along, how much has come down, how fast, and which source it is coming
  from (nothing for YouTube's own stream). A queue keeps its per-song list.
- **The paused icon is a quiet wave.** Playing shows the pixel wave with its peaks; paused now shows the same wave
  at a third of its amplitude — still a wave, visibly at rest. (The last build flattened it to a line, which read
  as "no music at all" — this is what it should have been.)
- **The notification icon says whether the music is running.** The small icon at the top left of the media player -
  in the shade, on the lock screen and in the quick settings player - is the pixel wave while it plays, and the same
  wave flattened to its own centre line while it is paused. That is state rather than animation, deliberately: a
  notification icon cannot animate (Android draws it statically, and re-posting it every second would flash the
  shade, get throttled and drain the battery), so it changes with playback, not with the sound.
- **A downloaded song says what it takes up.** Beside the downloaded badge in a track row - the Library's
  Downloaded list, and every playlist and album - the size of the copy is printed ("8.4 MB"), and a song's
  action sheet now says "Downloaded · 8.4 MB" instead of just "Downloaded". It measures the download itself
  rather than remembering a number, so one still arriving shows how much has really come down.
- **The Stats screen shows the requests the app made (temporary).** The Stats page - the headphone battery and
  download speed graphs - now ends with the last 200 requests this app sent: method, address, status and how
  long each took, with the failure written down when there was no answer, and a Clear button. It is meant to be
  temporary: something to read off the phone while the app is being worked on, and it comes out the same way it
  went in. In memory only, nothing on disk, nothing sent anywhere.
- **A downloaded song can be upgraded to a better copy.** The quality pill on the Now Playing screen opens
  the sources sheet - what the song could come from, with the quality of each - and every row there (Monochrome's
  FLAC, the Internet Archive, Audius' 320 kbps upload, the SoundCloud backup, YouTube) now has a download button.
  Tapping one downloads the song from *that* source, and a copy already on the phone is replaced by the new one:
  that is the upgrade - a downloaded song moves from YouTube's stream to a lossless FLAC, keeping its place in the
  library, its likes and its playlists. The switches that turn a source off for playback (Hi-Fi sound, and each
  source's own switch) turn it off here too, and the row says so rather than failing; a source that has nothing for
  the song falls back to YouTube's copy, so the download still lands.
- **The icon is a sound wave made of pixels.** One flat black behind, one flat white glyph, nothing else:
  twenty-two columns of 3 units, each an odd number of cells tall about the axis, in four bursts whose shoulders
  step in twos - a one-cell line the whole way with peaks on it, not a smooth envelope. (The first attempt kept it
  mirror-symmetric, which read as a lens with a pupil in the middle, so the mirror is gone.) The launcher, themed,
  notification, Android Auto, in-app and Desktop icons are all the same mark.
- **A pixel-art "S"** - SimpMusic's own initial, which also reads as a sound wave. Unique this time:
  nothing is copied from anywhere. Black and white only, on a 16 x 16 pixel grid, white on black.
  Themed, notification, Android Auto, in-app and Desktop icons are the same mark.
- **The icon is Monochrome's own mark now** - their exact 3 x 3 pattern, the diagonal cells empty, white
  on black, at your request. Worth knowing: it is another app's logo, and this build uses their service
  as a music source, so if it ever has to change back, our own play mark is one edit away.
- **The icon is a 3 x 3 pixel mark now**, in the same spirit as monochrome.st's own: a tiny
  black-and-white pixel pattern - a play triangle here, not their diagonal - white on black, nothing
  else. Themed, notification, Android Auto, in-app and Desktop icons are the same mark.
- **The New releases row is off the home page.** It was YouTube's own shelf on the home feed - the
  same page for every account - so it never read as yours, whatever order we put its items in. It is
  dropped now, and so is the feed's Music videos row. (If you want a new-release row built from your
  own artists later, that would have to be a row the app assembles itself, not one YouTube sends.)
- **A black-and-white pixel-art icon.** A chunky pixel play triangle, 9 x 10 pixels on a 16 x 16
  grid, white on black - nothing else. Themed, notification, Android Auto, in-app and Desktop icons
  are the same pixel mark.
- **Updates download themselves.** The APK is fetched as soon as a newer build is found - over Wi-Fi
  or Ethernet only, so a metered plan is left alone - which leaves a single **Install** tap with
  nothing to wait for. Android's own "Install?" prompt is the one confirmation left: no app can skip
  it, and F-Droid behaves the same. Waving an update away is remembered for that version, so it
  stops asking on every launch; Settings -> Install downloaded update is still there.
- **Two duplicate rows are gone from the home page.** The app's own "New releases" and "Music
  videos" shelves - the ones that sat above Moods & Moments - are no longer drawn. The home feed has
  a new-release row of its own, and that is the one ranked by what you listen to.
- **A pixel-art icon**, in the spirit of monochrome.st's mark: a chunky play triangle with a
  staircase sound wave under it, on a 16 x 16 pixel grid - one flat blue behind, one flat white
  glyph. Launcher, themed (monochrome), notification, Android Auto, in-app and Desktop icons are all
  the same pixel mark.
- **A minimalist app icon.** The icon is now in the monochrome mark's own terms: one flat blue behind
  (`#2B50F2`), one flat white glyph - no gradient, no glow, no shadow. The launcher, themed
  (monochrome), notification, Android Auto, in-app and Desktop icons are all the same flat mark.
- **The new-release row on the home feed is now the one that is ranked.** That row under Quick picks
  is YouTube's own shelf on the home feed, and nothing touched it: the app's ranked shelf is drawn
  much further down the page. The feed's shelf is now ranked as well, recognised whatever the app's
  language (by its title or by the page its "More" opens). Artists you **follow** count as history
  too, so the row has something to go on even before there is play history.
- **A modern app icon.** The play-and-wave mark has been redrawn: one confident wave through the
  button instead of two tight squiggles, so it still reads at launcher size. The themed (monochrome)
  icon, the in-app logo, the notification icon and the Desktop icons are all the same new mark.
- **New releases: matched by name as well as channel id.** YouTube sends many of the releases on that
  shelf without the artist's channel id, and such a release could never match your history - which is
  why the row could still read as random. A release now also matches when one of its artist names is
  an artist you play (case, spacing and a " - Topic" suffix ignored). The log line (Settings -> App
  log, search `NewReleases`) now also samples the first artist names from your history and from the
  shelf, so a mismatch can be seen at a glance rather than guessed at.
- **One bar in Podcasts, not two.** The tab had a field to search Apple's directory by name and
  another to paste an address. There is now one: type a name and it searches as you type; paste a
  link - an RSS feed, a podcast page, a YouTube channel or playlist - and the lens turns into a
  **+**, which follows that address. The same field does both, so there is no guessing which bar a
  link belongs in.
- **New releases: the ranking now reads a second history store.** The ranking added in 2.4.16 read
  the playback events, which are only kept while **local tracking** is on - so with it off, the row
  stayed exactly as YouTube sent it. It now also reads the local library's own play counter
  (all-time, kept whatever that setting says), and it writes what it found to Settings -> App log
  (search `NewReleases`: how many artists were found and how many shelf items were kept), so this
  can be checked rather than guessed.
- **New releases are the ones you'd want.** The "New releases" row came from YouTube's
  `FEmusic_new_releases` page, which is the same for every account - so nothing on it was chosen from
  what you listen to. It is now put in this phone's own order: releases by artists you have played in
  the last 180 days come first, most played first, and when there are six or more of those the
  unrelated ones are dropped, so the row really is "new from your artists". Fewer than six: they lead
  and the rest stays below. With no play history the row is left exactly as YouTube sent it. All of
  this is local; nothing leaves the phone.
- **The ANC strength slider reads like Sennheiser's own.** The track is now a ramp from soft to full
  instead of a bar that fills up, so which end is stronger is visible at a glance, with the "aware"
  and full-ANC glyphs marking the ends, lined up with the knob's travel.

Earlier updates:

- **A better voice for the spoken mode cue, and no more on-screen messages (2.4.15).** The cue says
  "Noise cancelling" (words, not the letters A-N-C), "Adaptive", "Transparency" and "Off" in a
  smoother high-quality voice (Piper's `en_GB-cori-high`, public domain). The one-off messages that
  were added to diagnose the silent cue are gone - it works, and it is logged in Settings -> App log.
- **The spoken mode cue is shorter and clearer (2.4.14).** It now says just the mode - "ANC", "Adaptive",
  "Transparency", "Off" - in a cleaner studio voice (public domain), so each cue is under a second
  instead of up to one and a half. The music is held down for 1.8 s instead of 2.5 s to match.
- **The update dialog's progress is on the same line as Cancel (2.4.14).** The number now sits inside the same
  row as the Cancel button, so it cannot drift from it, and the duplicate number under the progress
  bar is gone - one number instead of two.
- **The spoken mode cue no longer needs the phone's text to speech (2.4.13).** The cue was silent because this
  phone has no speech engine installed at all - so every earlier attempt to say the mode name was
  silence, however it was triggered. The four names now ship inside the app as small audio clips (a
  public-domain voice, generated offline), played through the same audio path as the music: no engine,
  no voice download, no permission. The music is still briefly turned down so the name is heard over
  it.
- **The spoken mode cue was being drowned by the music, and now isn't (2.4.12).** The app's own player holds
  one audio-focus request and is built not to duck on focus, so asking for focus never lowered the
  music - the mode's name was said underneath it at full volume. The app's own player is now asked to
  duck directly (the same gain the sleep timer fades with, so the user's volume is untouched and the
  slider does not move), the name is said 300 ms later over a quiet music bed, and the volume is put
  back after 2.5 s. For the first three cues of a run a one-line message also says what happened
  (which change, what was said, whether a voice is installed), so a silent cue can be reported without
  reading the log.
- **The update dialog's percentage sits on the same line as Cancel (2.4.11)**, instead of riding high beside it.
- **The headphones' spoken mode cue is being chased down (2.4.10).** If you only ever hear the headset's own
  tone, this build now writes what the cue does to Settings -> App log at Info level (search
  "HeadsetCue"): whether the speech engine came up, whether the headset reported the change, and
  what was said. The cue also no longer waits on the app's read-back of the write (a write can land
  and still read back oddly), the mode is said 400 ms after the music starts ducking instead of into
  the first beat of it, and a speech engine that failed to start is no longer permanent.
- **The update installer is fixed (2.4.8).** The app kept the APK it had downloaded before and offered to
  install *that* file instead of fetching the new release — and installing an older APK over the app is
  exactly what Android refuses with its bare "App not installed". Every APK is now checked before it is
  offered or handed to the installer: it must be a complete, readable APK, for this app, signed with the
  same key as the installed app, and newer than the installed version. A file that fails is dropped, and
  the real reason (stale file, different signing key, incomplete download) is shown in the dialog instead
  of "App not installed".
- **The headphones say the mode as soon as it changes (2.4.6).** The cue now speaks the moment the app
  switches ANC, and also when the headset reports a change the app did not make (its own ANC button). A
  report of a change the app just made is not spoken twice.
- **Fix: the app could crash on launch (2.4.5).** The Statistics screen's navigation route was missing the
  serialization marker AndroidX Navigation needs, and the app builds its routes at startup — so 2.4.5 could
  die before showing anything, with "An unexpected error occurred". Fixed. If you are on 2.4.5, install this
  over it.
- **The self-update is more reliable.** A download now goes to a temporary file, is checked to be a real APK,
  and only then replaces the last one — so a download that failed halfway can no longer look like a ready
  update that the installer rejects. If you have not allowed this app to install updates, it now opens that
  setting instead of silently doing nothing. A failed download or install is shown in the dialog, which stays
  open, rather than closing as if it worked.

- **Statistics graphs.** Settings → Statistics now has two line charts: the connected headphones' battery
  over time (drawn from the readings the app already saves), and the download speed over time (the player
  samples it while playing). Everything stays on the device. Each shows a peak; with too little history yet
  it says so rather than drawing a guess.

- **The notification line shows the bitrate and the time left, not the download speed.** It now reads, for
  example, `FLAC 16/44.1 · 80% · ~12h`: the song's quality and bitrate, the headphones' battery, and an
  estimate of how long they will last. (The download speed is gone from it.)
- **Monochrome reports a bitrate.** Its FLAC now shows the file's average bitrate (worked out from its size
  and the song's length), e.g. `FLAC 1100 kbps`, instead of just `FLAC`.
- **The MOMENTUM 4 cue starts sooner.** The speech engine is prepared as soon as the headphones connect, so
  the spoken mode name is not missed on the first switch.

- **The stats line reaches more Android versions.** The quality/speed/battery line is now written to the
  session metadata's subtitle as well as its artist, so whichever field your Android build's media player
  reads (the lock screen and quick-settings player draw from the session metadata on Android 13+), it shows.

- **The download speed in the notification now updates.** It follows the bytes actually being downloaded
  (over the last two seconds) rather than the player's slow long-window average, so it moves while a song
  loads and drops away when nothing is being fetched. It is refreshed every 3 seconds while playing.
- **The insights now show on Android 13+ too (including Android 17).** On those versions the media player is
  drawn from the session metadata, not the notification text, so the quality, speed and battery are now put
  on the metadata's second line — where the lock screen and quick-settings player actually read them.

- **Insights in the notification.** The Android media notification (lock screen and quick-settings player)
  now shows the stream's quality, the download speed and the headphones' battery on its second line, e.g.
  `Queen · FLAC 16/44.1 · 2.4 MB/s · 80%`.
- **A clearer update download.** The progress is a bar with a percentage, shown inline in the update dialog,
  instead of a bare number on the button.
- **Finish an update later.** A downloaded update is kept, so if you leave the installer (or the dialog) you
  can install it without downloading again: the update dialog says "Install", and Settings has an "Install
  downloaded update" entry.

- **Podcasts get their own playback speed.** The speed sheet now has a separate "Podcast speed" next to the
  song speed, so an episode can be sped up without changing how songs play. The player picks the right one
  per track.
- **The speed control works with crossfade on.** It used to be greyed out whenever crossfade was enabled (a
  desktop limitation). On Android the speed is applied through the crossfade — the fade itself scales with
  your speed — so the control is now live there.

- **Find a podcast by name.** The Podcasts tab can now search Apple's public podcast directory: type a name
  in the new search field and tap a result to follow it, instead of only pasting an RSS feed or a YouTube
  link.

- **Cleaner buttons in the player.** The two pills under the seek bar — the headphones' noise control and the
  song's source — now share one shape: a full rounded pill with a hairline border and a slightly larger icon,
  so they read as a matching pair rather than two different badges.

- **How long the headphones have left.** The player's headset pill now shows an estimated play time next to
  the battery percentage (e.g. `80% · ~12h`). Headsets report only a percentage, so the time is learned from
  how that percentage falls over time on this phone; it appears once there is enough history to trust it (at
  least about half an hour and a few percent of drop), and says nothing before that.

- **Less work in the background.** The download-speed figure in the notification is now refreshed only when
  it actually changes, and every 10 seconds rather than every 5, so the notification is re-posted far less
  while a song plays. The figure inside the app updates every 2 seconds instead of every second.

- **Lyrics no longer tell a third party what you play.** The default lyrics provider is now LRCLIB (a
  public, account-free lyrics database) instead of the SimpMusic server. The SimpMusic provider is still
  available in Settings if you want it. An audit for this build found no advertising or analytics code at
  all, and no playback reporting.

- **The download speed is in the notification too.** The speed that was only inside the app now shows on the
  second line of the Android media notification (the lock screen and the quick-settings player), next to the
  artist, e.g. `Queen · 2.4 MB/s`, refreshed while the song plays.
- **The MOMENTUM 4 cue is now audible over music.** The spoken mode name is played as media audio, so it
  comes out of the headphones rather than the phone's speaker, and the music is ducked for it, so it can be
  heard over a song that is playing.

- **The app updates itself.** "Check for update" now downloads the new test build inside the app and hands
  it to Android's installer — no browser, no copy-pasting a link. It shows how far the download has got,
  and Android still asks you to confirm the install, as it must for any app. On the desktop, the download
  page still opens in the browser.
- **Download speed in the player.** Next to where the song comes from, the player now shows how fast it is
  coming in, e.g. `YouTube · OPUS 160 kbps · 2.4 MB/s`. The bitrate was already there; the speed is new.
- **Monochrome shows in the source list.** It is now listed like the Internet Archive — shown while the
  search runs, and as not found when it has nothing — instead of only appearing once a file was found.
- **A spoken cue for the MOMENTUM 4.** When the app changes the noise mode, it says which one through the
  headphones ("Noise cancelling", "Adaptive noise cancelling", "Transparency", "Noise cancelling off"),
  because the headset's own tone barely differs between modes. Android's text to speech, in English.

- **Monochrome as a lossless source.** With Hi-Fi sound on, the app now also looks for the same recording
  as a lossless FLAC on Monochrome (TIDAL's catalog, streamed through `tracks.monochrome.st`), beside the
  Internet Archive. The two are searched at the same time and the first to answer wins, so a slow
  archive.org search no longer holds back a file that is ready. Every stream is read before it is used: one
  that does not answer with FLAC is skipped and the song carries on as before. It has its own switch in
  Settings → Playback, next to the Internet Archive's.

- **Each noise mode now has its own icon.** With the Sennheiser MOMENTUM 4 connected, the button in the
  player notification, the lock screen and Android's media controls showed the same icon for "Noise
  cancelling" and "Adaptive ANC", so you could not tell them apart at a glance. Adaptive ANC now has its
  own icon, beside the ones Noise cancelling, Transparency and Off already had. The player's own badge
  and the mode picker show it too.
- **Updates come from this repository.** "Check for update" and the check at startup now look here for the
  newest test build and download its APK from the release, instead of opening the official SimpMusic
  download page. The check at startup follows the app's "auto check for updates" setting (on by default).

- **A Podcasts tab.** Paste an address in the field at the top to follow a podcast. It can be:
  - an RSS feed, such as `https://darknetdiaries.com/feedfree.xml`;
  - a podcast's web page (the app finds its feed);
  - a YouTube channel (`youtube.com/@lexfridman`, `/channel/…`);
  - a YouTube playlist.

  The tab shows the podcasts you follow, their newest episodes together, and recommendations. Open a podcast to
  see all its episodes, follow or unfollow it, or check for new ones.
  - RSS episodes play from the podcast's own audio file. YouTube episodes play like any YouTube video.
  - Every episode remembers where you stopped and continues from there, wherever you start it from. Episodes
    you finished are marked as played.
  - Recommendations come from Apple's public podcast directory, searched with the topics of the podcasts you
    follow (nothing about you or what you play). You can follow one in one tap, or open it and listen first.
  - Everything is kept on your phone. YouTube channels show their latest 30 videos, and keep the ones seen
    before.
  - YouTube's own channel feeds are currently down for everyone (they answer "not found"), so the app reads
    channels the way YouTube's website does.
  - Episodes are never sent to lyrics or canvas services, and never searched for on the Internet Archive or
    Audius.
- **Turn each high-quality source on or off.** With Hi-Fi sound on, Settings → Playback now has a switch for
  the Internet Archive and one for Audius. YouTube is always there, and the SoundCloud backup keeps its own
  switch. The sources sheet shows a source you turned off as off. The best available copy is still picked
  automatically: lossless first, then Audius, then YouTube.
- **Analytics' back arrow, refined.** It is hidden when Analytics is opened from the tab bar, and shown when
  you reach it from another screen.

- **Lossless and Audius songs play to the end.** The player read every song in 5 MB pieces. For the
  Internet Archive's FLAC files and Audius's MP3s, the end of a piece looked like the end of the song.
  A lossless song stopped after about 45 seconds (or about 13 seconds when the file carries a large
  cover picture), an Audius song after about two minutes, and you couldn't skip forward past the first
  piece. These sources now play in one go.
- **Only real releases count as high quality.** A better-quality copy is now used only if it is the
  actual digital release. Concert tapes and bootlegs, transfers from vinyl, cassette or 78 rpm records,
  session takes and alternate versions are skipped, and so are files too quiet to hold music.
  Copies that earlier builds had already picked are checked again under these rules.
- **Songs start sooner.** A song whose YouTube address was looked up in the last ten minutes on the
  same network now starts without checking that address with Google first (that check cost a
  connection, about a quarter to half a second). Playback also starts before the app finishes some
  bookkeeping.
- **Better battery life.**
  - With the screen off, the app updates the song position once a second instead of 20 times
    (4 times a second with SponsorBlock on).
  - Songs loaded ahead for instant skipping keep 30 seconds ready instead of downloading 200 seconds
    each.
  - With Battery Saver on, the app loads one song ahead instead of three, and caches no openings.
  - Lyrics and canvas videos load when you look at the app, not for every song played with the
    screen off.
  - The friends feature only connects while you have friends and the app is open.
- **More privacy.**
  - The lyrics and canvas services no longer hear about songs you play with the screen off, unless
    you open the app.
  - The app no longer contacts the SimpMusic developer's GitHub on every launch. That file is only
    needed for DJ crossfade.
- **Keep free storage.** In Settings → Storage, the player cache can now leave a share of your phone's
  storage free (20% by default; off, 10%, 15%, 25% and 30% are the other choices). When free space drops
  below it, the oldest cached songs are removed. This also catches space taken by other apps, and both
  cache settings now apply without restarting the app.
- **AI features without an API key, on your phone.**
  - Without an AI key, "Your music taste" in Library is now written on your phone from your listening.
    Nothing is sent anywhere, and the card says "written on this phone".
  - Playlist suggestions (the ✨ button) now work for every playlist, not only ones synced to a YouTube
    account. They come from YouTube radios of a few songs in the playlist, picked on your phone, with
    no account and no AI key. Reload gives suggestions based on other songs in the playlist.
- **Analytics' back arrow is gone when you open it from the tab bar.** It only took you to Home. It
  still shows when Analytics is opened from somewhere deeper in the app.

- **A heart in the media controls.** The like button is now the first button in the notification,
  the lock screen and Android's quick settings player, so you can like a song without opening the app.
  The heart fills in straight away, also when the app is closed. Android shows only two extra buttons
  there, so the second one is noise control while your MOMENTUM 4 or Huawei/Honor earbuds are
  connected, and Shuffle otherwise.
- **Noise control from the notification no longer pauses your song.** The MOMENTUM 4 pauses music
  when transparency turns on (a setting in Sennheiser's app). The app now ignores the headphones'
  pause and play while it is switching the mode, so the song keeps playing. The headset's own touch
  gesture still works as you set it up.
- **Smoother noise-control switching.** Tapping the button changes it at once. The headphones are only
  switched once you stop tapping, so going from noise cancelling to off in three quick taps no longer
  passes through adaptive and transparency on the way. Switches on the MOMENTUM 4 also take about half
  as many messages to the headset as before.
- **Clearer labels.** The button now reads like the label in the player: "ANC · 80%", "ANC · Comfort",
  "Adaptive ANC", "Transparency", "ANC off".

- **Music on Home without signing in.** Signed out, YouTube Music only offers podcasts and an artist
  picker on its Home. The app now opens Home with three shelves of its own:
  - **Quick picks**: radios of the songs you play most on this phone, mixed together;
  - **New for you**: songs from those radios you have never played;
  - **Listen again**: your most played songs.

  On a fresh install with nothing played yet, Quick picks start from today's top music videos instead.
  Sign in and YouTube's own Home takes over again.
- **Shuffle and noise control in the player notification.** Shuffle became one of the two buttons
  shown in the notification, the lock screen and Android's media controls (since replaced by the heart). Next to it, while your MOMENTUM 4 or
  Huawei/Honor earbuds are connected, a button shows the noise mode: noise cancelling (with its strength),
  adaptive, transparency or off. Tap it to switch to the next mode. Like, repeat and radio follow where
  there is room. The button disappears a minute after music stops, so the headphones' own app can
  connect to them again.

- **Listen Together connects by itself.** Opening Listen Together connects straight away: rooms on
  your Wi-Fi show up, and **Create room** and **Join room** work without tapping Connect first. If you
  leave the screen without joining a room, it disconnects again.
- **Everyone in a room can control playback.** Guests can now play, pause, skip, seek and pick songs
  for the whole room from their own player. Each request is carried out on the host's phone, so the
  room keeps one queue and everyone hears the same next song. The host can turn this off with
  **Everyone can control playback** in the room (it is on by default, and Listen Together settings has
  the same switch for new rooms). A phone call on a guest's phone pauses only that phone.
- **Listen Together fixes.** Guests no longer jump back when the host's queue grows (endless queue)
  or when the host approves a suggestion. An approved suggestion now goes into the queue instead of
  playing at once on guests' phones. Guests no longer jump to the start of the song and back when
  someone joins or leaves, or when the host changes. The next song no longer restarts a second in on
  guests' phones, and songs already played no longer come back after the current one. The screen no
  longer gets stuck on "Connecting".
- **A second high-bitrate source: Audius.** With Hi-Fi sound on, when the Internet Archive has no
  lossless copy of a song, the app looks for the artist's own 320 kbps upload on
  [Audius](https://audius.co), a free music service (no account needed). Only uploads by the artist's
  own account are used, never other people's copies. Coverage is small: mostly electronic and
  independent artists who publish there. Of 14 well-known songs I tried, it had 2. Most songs still
  play from YouTube. As with lossless, a song starts at once and moves to the better copy mid-song.
- **Fake lossless is skipped.** Internet Archive files named after a YouTube upload or a download
  site ("Official Audio", "y2mate") are no longer used: they hold YouTube's own audio in a bigger file.
  For the same reason, the Internet Archive's MP3 uploads are not used as a high-bitrate source.
- **Fewer stalls at the start of a lossless song.** A song now starts on the lossless file only when
  about 9 seconds of it are already downloaded. Otherwise it starts on YouTube and switches mid-song.
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
- **Connects when you open it.** There is nothing to tap before creating or joining a room.
- **Everyone can control playback**: guests play, pause, skip, seek and pick songs for the whole room
  from their own player, unless the host turns **Everyone can control playback** off in the room.
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
[SimpMusic-source-3b5d851.zip](SimpMusic-source-3b5d851.zip) is the complete source code this build was
made from, including the changes above: the app at commit `3b5d851` and its `core` module at `e48f691`.
Build it with `./gradlew :androidApp:assembleOptimized` (an unsigned release-type APK, to sign with
your own key) or `./gradlew :androidApp:assembleDebug` (Android SDK and JDK 21 required).
