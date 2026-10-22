<div align="center">

<h1>Harla</h1>

<p><strong>Roasting software for coffee roasters. The same coffee, every time.</strong></p>

<p>
  <a href="https://github.com/cenkgundev/harla-releases/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/cenkgundev/harla-releases?label=release&color=C26A12"></a>
  <img alt="Platform" src="https://img.shields.io/badge/macOS-12%2B%20%C2%B7%20Apple%20Silicon-1A1815">
</p>

<p>
  <a href="https://harla.coffee/en/">Website</a> ·
  <a href="https://github.com/cenkgundev/harla-releases/releases/latest">Latest release</a> ·
  <a href="mailto:demo@harla.coffee">Contact</a>
</p>

</div>

---

This repository hosts the installers for Harla. The source code is not public.

Harla connects to a coffee roaster, draws the roast live, compares it with your profile and tells you when first crack is coming. The roasting computer saves every roast locally first and syncs it to the cloud, so an iPad or iPhone can follow the roast live and browse the roast history and green coffee stock. Harla reads 273 roaster and thermometer models over Modbus, Siemens S7, WebSocket, Phidget, Yoctopuce and serial protocols.

> **Türkçe:** Kahve kavurma yazılımı Harla'nın kurulum dosyaları. Ayrıntılar için [harla.coffee](https://harla.coffee).

## Download

Latest release: **[Harla 1.4.0](https://github.com/cenkgundev/harla-releases/releases/tag/v1.4.0)** (October 19, 2026)

| Platform | File | Size |
|---|---|---|
| macOS, Apple Silicon (M1 and later) | [Harla-1.4.0.dmg](https://github.com/cenkgundev/harla-releases/releases/download/v1.4.0/Harla-1.4.0.dmg) | 115 MB |
| macOS, Intel | Not available yet | |
| Windows | Not available yet | |

Earlier versions are on the [Releases](https://github.com/cenkgundev/harla-releases/releases) page. Once installed, Harla offers new versions itself.

## System requirements

- macOS 12 Monterey or later
- A Mac with Apple Silicon (M1 or later)
- About 200 MB of disk space
- An internet connection to sign in and sync. Recording a roast works offline; Harla syncs when the connection returns.

The app bundles its own Java runtime. You don't need to install Java.

## Install on macOS

1. Open `Harla-1.4.0.dmg`.
2. Drag **Harla** into the **Applications** folder.
3. Open Harla from Applications. The app carries a Developer ID signature and Apple's notarization, so macOS asks once whether to open an app downloaded from the internet. Click **Open**.
4. Enter your e-mail address and the 6-digit code Harla mails you.
5. In **Settings › Machine**, pick your roaster model, the connection type and the port.

To check the installation, run this in Terminal. Each line should start with `ok`, and the last line should read `all ok`:

```bash
/Applications/Harla.app/Contents/MacOS/Harla --self-check
```

Harla keeps its local database in `~/Library/Application Support/Harla/`. Deleting the app leaves that folder in place.

## Verify a download

GitHub publishes a SHA-256 digest for each file. You can see it next to the file on the release page, or print it with the GitHub CLI:

```bash
gh release view v1.4.0 -R cenkgundev/harla-releases --json assets -q '.assets[] | .name + "  " + .digest'
```

Compare it with the digest of the file you downloaded:

```bash
shasum -a 256 Harla-1.4.0.dmg
# fad067c83d2ed9527573aeecaeeb943c976f2b076c62e2fe31a4f0592ff96ec9
```

To confirm Apple's signature and notarization:

```bash
spctl -a -t open --context context:primary-signature -vv Harla-1.4.0.dmg
# accepted, source=Notarized Developer ID
```

## Support

For a demo, an account or help with your roaster, write to [demo@harla.coffee](mailto:demo@harla.coffee) or visit [harla.coffee](https://harla.coffee/en/).

## License

Harla is proprietary software. © 2026 Harla. All rights reserved. You need a Harla account to use it.

Harla includes open-source components. You can read their licences in **Settings › About**.
