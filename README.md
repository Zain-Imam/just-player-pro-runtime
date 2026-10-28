# Just Player Pro runtime

Files that [Just Player Pro](https://github.com/Zain-Imam/just-player-pro) downloads when you turn on
**Settings → Websites**, so it can play YouTube and other sites with
[yt-dlp](https://github.com/yt-dlp/yt-dlp). They are not part of the app, so the app stays the same size
for everyone who never turns this on.

Each release holds one zip per device type (arm64-v8a, armeabi-v7a, x86, x86_64) with:

- **Python**, trimmed of what yt-dlp never uses (tests, IDLE, Tk). For 64-bit devices it is the official
  build from [python.org](https://www.python.org/downloads/android/), checked against its signature.
  python.org has no 32-bit build, so those are built from the same Python release with Python's own
  Android build script.
- **QuickJS-ng**, built from [its source](https://github.com/quickjs-ng/quickjs), for YouTube pages that
  need JavaScript solved.

yt-dlp itself is not here: the app downloads it from yt-dlp's own releases and checks it against
yt-dlp's checksums.

Everything is built by the workflow in this repository, and each release links to the run that made it,
so you can see exactly where every file came from. The app knows the SHA-256 of each zip and refuses
anything else.

## Licences

Python is under the [PSF License](https://docs.python.org/3/license.html) (its `LICENSE.txt` is inside
each zip, with the licences of OpenSSL, SQLite and the other libraries it includes). QuickJS-ng is under
the MIT License (`LICENSE-quickjs.txt` in each zip).
