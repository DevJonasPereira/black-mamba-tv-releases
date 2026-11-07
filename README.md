# Black Mamba TV

![Black Mamba TV](banner_tv.png)

Signed builds of Black Mamba TV, the family media app, for Fire TV / Android TV and for
Android phones and tablets. Both versions have Tailscale built in, so they reach the home
media server from anywhere. They also set the server up by themselves, put Anime first, and
have a **Calendar** of upcoming episodes. Both apps can request movies and series through
Seerr, using the same sign-in as for watching. Both apps are made for the Black Mamba home server only, so there's no server
to choose. Several Jellyfin users can share one device, which is handy on a family tablet.

- **The TV app** is a private build of [Wholphin](https://github.com/damontecres/Wholphin).
- **The phone app** is a private build of
  [Findroid](https://github.com/jarnedemeulemeester/findroid).

Each release contains both apps under one version number, and installed copies update
themselves from this repository. The source is kept in separate private repositories, and
every release includes the matching source archives.

## Which file do I need?

Every file is in the [latest release](https://github.com/DevJonasPereira/black-mamba-tv-releases/releases/latest).

| Device | App | File to install | Needs at least |
|---|---|---|---|
| Amazon Fire TV: every Stick (Lite, HD, 4K, 4K Max), Cube, and TVs with Fire TV built in | TV | `BlackMamba-release-armeabi-v7a.apk` | Fire OS 6 |
| Google TV / Android TV: Chromecast with Google TV, Onn, Nvidia Shield, Sony, TCL, Hisense, Philips | TV | `BlackMamba-release-armeabi-v7a.apk` | Android 6 |
| A TV you're not sure about | TV | `BlackMamba-release.apk` (works on every TV, bigger download) | Android 6 |
| Android phone: Samsung Galaxy, Google Pixel, Motorola, Xiaomi, OnePlus and so on, from about 2017 on | Phone | `BlackMambaTV-Mobile-release-arm64-v8a.apk` | Android 10 |
| Older or cheaper Android phone that's 32-bit only | Phone | `BlackMambaTV-Mobile-release-armeabi-v7a.apk` | Android 10 |
| Android tablet, including Amazon Fire tablets on Fire OS 8 | Phone | `BlackMambaTV-Mobile-release-arm64-v8a.apk` | Android 10 |
| A phone or tablet you're not sure about | Phone | `BlackMambaTV-Mobile-release.apk` (works on every phone, bigger download) | Android 10 |
| iPhone, iPad, Apple TV, Roku, Samsung or LG smart-TV apps | Not supported | | |

If a file won't install ("App not installed" or "There was a problem parsing the package"),
use the one that works everywhere for that device: `BlackMamba-release.apk` on TVs, or
`BlackMambaTV-Mobile-release.apk` on phones. Updates later pick the right build for the device
automatically.

### What each device needs to connect

- **Permission to install apps from outside the app store:** the Downloader app on a Fire
  TV, or your browser on a phone. Black Mamba TV asks for the same permission once, the first
  time it installs an update.
- **At home on the home Wi-Fi:** nothing else. It connects to the server directly.
- **Anywhere else, including mobile data and other people's Wi-Fi:** a one-time Tailscale
  sign-in. The TV shows a QR code to scan with a phone, and the phone app has a **Sign in to
  Tailscale** button. Use a Tailscale account that has been given access to the media server.
  If the device needs approval, or the account is on a different Tailscale network, the app
  says so and carries on by itself once it's sorted.
- **One sign-in:** once connected, the app shows a single username and password sheet. It
  signs you in to watching (Jellyfin) and to requests (Seerr) together.
- **To request movies and series:** open **Discover** (the TV's side menu or the phone's
  tab). If you were signed in before this version, Discover asks once for the same username
  and password.
- **To approve requests (admins, phone app):** Discover starts with **Waiting for your
  approval**. Tap a title to approve or decline it, or tap **Manage requests** for the full list,
  where you can also retry or delete requests.
- **To see upcoming episodes:** nothing extra. Open **Calendar** in the TV app's side menu or
  the phone app's Calendar tab. It lists new episodes of the series the server follows.

## Install on a Fire TV

1. On the Fire TV, open **Find → Search**, then search for and install **Downloader** (by
   AFTVnews).
2. Go to **Settings → My Fire TV → Developer options → Install unknown apps** and turn
   **Downloader** on. If Developer options is missing, open **Settings → My Fire TV →
   About** and click the device name 7 times.
3. Open Downloader and enter this address:

   ```
   https://github.com/DevJonasPereira/black-mamba-tv-releases/releases/latest/download/BlackMamba-release-armeabi-v7a.apk
   ```

   Then choose **Install**. If it won't install, use the same address ending in
   `BlackMamba-release.apk` instead.
4. Open **Black Mamba TV**. If it can't reach the server directly, it shows a QR code. Scan the
   code with a phone and sign in to Tailscale. This only needs doing once.
5. Sign in with your username and password. That covers watching and requests.

On other Android TVs, sideload the same APK the way you normally would.

## Install on an Android phone or tablet

Needs Android 10 or newer.

1. On the phone, open this link in the browser:

   ```
   https://github.com/DevJonasPereira/black-mamba-tv-releases/releases/latest/download/BlackMambaTV-Mobile-release-arm64-v8a.apk
   ```

   That's the right file for almost every phone. On an older 32-bit phone, use the address
   ending in `BlackMambaTV-Mobile-release-armeabi-v7a.apk` instead.
2. Open the downloaded file. If Android asks, allow your browser to install unknown apps, then
   choose **Install**.
3. Open **Black Mamba TV** and tap **Sign in to Tailscale** if it asks. This only needs doing
   once.
4. Sign in with your username and password. That covers watching and requests (the
   **Discover** tab).

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
