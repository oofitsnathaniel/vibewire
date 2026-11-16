# Privacy and security

This page describes the Windows release.

## On your device

Vibe Wire keeps preferences, library paths, playback history, approved tool paths and fingerprints, and media metadata and artwork caches in your Windows user profile, primarily under `%LOCALAPPDATA%\VibeWire.Avalonia`. Downloads and exports go to the location you choose. Local playback works without a Vibe Wire account or an internet connection. Windows protects saved TMDB and Private Beta credentials for the current user when those credentials are kept between sessions.

## When Vibe Wire connects

| Feature | What goes online |
| --- | --- |
| **Updates and tool setup** | The update checker reads the current feed from GitHub. Stable needs no GitHub token. Private Beta sends the tester’s own token to GitHub for access. The tool preparation feature downloads selected tools from their configured providers. |
| **Media downloads and previews** | Tools such as yt-dlp contact the media sites for the URLs you submit. Enabling optional download features may contact their configured services, such as SponsorBlock. |
| **Metadata lookup** | MusicBrainz and YouTube default to **Local Only**. If you enable an online mode, lookups send the relevant search terms or media link to the provider. TMDB requests use your API Read Access Token and the movie or show search terms. |
| **Optional browser integration** | The local API uses a loopback listener and a session token when you enable it. Requests require review in Task Monitor before download. |

The site or service you contact has its own privacy terms. Locally approved third-party tools and scripts run with your user account’s permissions. Choose trusted files and approve them through Settings.

## Updates and Windows signing

The in-app updater checks the signature on a release manifest with the public key built into Vibe Wire. It checks the manifest against the expected release and then verifies the size and SHA-256 hash of the downloaded installer before handing it to Windows. The signed metadata is separate from Windows Authenticode.

The Windows 1.0.0 installer is **not Authenticode-signed**. Windows may show an unknown publisher or reputation warning. Use the [official GitHub release](https://github.com/oofitsnathaniel/vibewire/releases/latest). For a manual download, [check the SHA-256](RELEASING.md#release-files) against the checksum on that release.

## Bug reports

Opening the form lets you draft or copy a report. Choosing **Send report** submits the description, selected area, app version, and OS/architecture to the project’s Google Apps Script reporting service. Steps to reproduce, a follow-up email, and technical details are included if you provide or select them. Choose **Copy report** if you want to review or share the text yourself. Leave credentials, private paths, and personal information out of public GitHub issues.
