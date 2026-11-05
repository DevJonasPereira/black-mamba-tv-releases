# Black Mamba TV

![Black Mamba TV](banner_tv.png)

Signed builds of Black Mamba TV, the family media app, for Fire TV / Android TV and for
Android phones and tablets. Both versions have Tailscale built in, so they reach the home
media server from anywhere. They also set the server up by themselves and put Anime first.

- **The TV app** is a private build of [Wholphin](https://github.com/damontecres/Wholphin).
- **The phone app** is a private build of
  [Findroid](https://github.com/jarnedemeulemeester/findroid).

Each release contains both apps under one version number, and installed copies update
themselves from this repository. The source is kept in separate private repositories, and
every release includes the matching source archives.

## Install on a Fire TV

1. On the Fire TV, open **Find → Search**, then search for and install **Downloader** (by
   AFTVnews).
2. Go to **Settings → My Fire TV → Developer options → Install unknown apps** and turn
   **Downloader** on. If Developer options is missing, open **Settings → My Fire TV →
   About** and click the device name 7 times.
3. Open Downloader and enter this address:

   ```
   https://github.com/DevJonasPereira/black-mamba-tv-releases/releases/latest/download/BlackMamba-release.apk
   ```

   Then choose **Install**.
4. Open **Black Mamba TV**. If it can't reach the server directly, it shows a QR code. Scan the
   code with a phone and sign in to Tailscale. This only needs doing once.
5. Pick your Jellyfin user and sign in.

On other Android TVs, sideload the same APK the way you normally would.

## Install on an Android phone or tablet

Needs Android 10 or newer.

1. On the phone, open this link in the browser:

   ```
   https://github.com/DevJonasPereira/black-mamba-tv-releases/releases/latest/download/BlackMambaTV-Mobile-release.apk
   ```

2. Open the downloaded file. If Android asks, allow your browser to install unknown apps, then
   choose **Install**.
3. Open **Black Mamba TV** and tap **Sign in to Tailscale** if it asks. This only needs doing
   once.
4. Pick your Jellyfin user and sign in.

## Updates

Both apps check this repository when they start and tell you when a new version is out.

- **TV:** you get a message when an update is out. To install it, go to **Settings → Check for
  updates**.
- **Phone:** you get a dialog when an update is out. Tap **Install**.

The first time, Android asks you to allow Black Mamba TV to install unknown apps. Turn it on and
go back. Android only installs an update when it's signed with the same key as the installed
app.

## Files in each release

| File | What it is |
|---|---|
| `BlackMamba-release.apk` | TV app, works on every TV (use this one if unsure) |
| `BlackMamba-release-armeabi-v7a.apk` | TV app, smaller build for 32-bit TVs (most Fire TV Sticks) |
| `BlackMamba-release-arm64-v8a.apk` | TV app, smaller build for 64-bit TVs |
| `BlackMamba-release-x86_64.apk` | TV app, for emulators |
| `BlackMambaTV-Mobile-release.apk` | Phone app, works on every phone (use this one if unsure) |
| `BlackMambaTV-Mobile-release-arm64-v8a.apk` | Phone app, smaller build for most phones |
| `BlackMambaTV-Mobile-release-armeabi-v7a.apk` | Phone app, smaller build for older 32-bit phones |
| `BlackMambaTV-Mobile-release-x86.apk`, `-x86_64.apk` | Phone app, for emulators |
| `SHA256SUMS` | Checksums of the files above |
| `black-mamba-tv-source-*.tar.gz` | TV app source code (GPL-2.0) |
| `black-mamba-tv-mobile-source-*.tar.gz` | Phone app source code (GPL-3.0) |

## Checking a download

Every APK is signed with the Black Mamba TV key. Its certificate SHA-256 is:

```
53:42:37:E1:61:B8:47:96:AE:F0:75:0A:89:9A:4C:C8:CA:12:84:48:6D:94:4B:19:39:92:3A:7B:AC:99:65:A2
```

To check a file with the Android SDK build tools:

```sh
apksigner verify --print-certs BlackMamba-release.apk
sha256sum -c SHA256SUMS
```

## License

The TV app is based on Wholphin (GPL-2.0) and the phone app on Findroid (GPL-3.0). Each is
distributed under its upstream license, and the source for each version is attached to its
release. Tailscale's code is BSD-3-Clause.
