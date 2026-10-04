# Puros providers

Providers connect [Puros](https://github.com/purosapp/purosapp), a macOS music player built for audio quality, to streaming services. Each provider is a separate package that you install into Puros; Puros keeps your library, queue, decoding, DSP and audio output, and the provider handles sign-in, the service's catalog and preparing audio files.

This list links every known provider. To build your own, see the [Provider SDK](https://github.com/purosapp/puros-provider-sdk).

## Installing a provider

1. Open the provider's **Releases** page and download `puros-provider-<id>-<version>.zip`.
2. Optionally check the download against the `.sha256` file next to it: `shasum -a 256 -c puros-provider-<id>-<version>.zip.sha256`.
3. In Puros open **Settings → Accounts → Install provider…** and choose the ZIP.
4. Read the consent dialog: it lists the services the provider contacts, the secrets it stores, the helper programs it runs, and any warnings (for example an unsigned package). Install only if you trust the author.

Later versions install with **Update from file…** on the installed provider. Disabling or removing a provider keeps its data until you remove that too.

## Official providers

Official providers are developed and maintained by the Puros project.

_None yet._ The local library, M3U playlists and Last.fm scrobbling are built into Puros and need no provider.

## Unofficial providers

> [!WARNING]
> **Unofficial providers are not part of Puros.** They are third-party software, published by their authors in their own repositories. The Puros project does not develop, review, audit, sign, endorse or support them, and is not responsible for how they work, for any damage, data loss or account restrictions they cause, or for their compliance with the terms of the services they connect to.
>
> - Providers are **not sandboxed**: they run with full access to your files and network as your user. Install only providers whose source you trust.
> - None of these providers is affiliated with, authorized or endorsed by the service it connects to. Service names and logos belong to their owners.
> - Using a service through an unofficial client may break its terms of use and can lead to your account being restricted. You use them at your own risk.
> - Report problems to the provider's repository, not to Puros.

| Provider | Author | Account | Notes | Source | Download |
| --- | --- | --- | --- | --- | --- |
| SoundCloud | [@jacobbvfx](https://github.com/jacobbvfx) | Optional | Public tracks work signed out; sign in for your library and Go+ streams. Streams AAC or MP3 unchanged; optional original uploads when the artist allows downloads. | [puros-provider-soundcloud](https://github.com/jacobbvfx/puros-provider-soundcloud) | [Latest](https://github.com/jacobbvfx/puros-provider-soundcloud/releases/latest) |
| Spotify | [@jacobbvfx](https://github.com/jacobbvfx) | Premium | Catalog and library through the Web API (your own Client ID), playback prepared by librespot. Ogg Vorbis up to 320 kb/s. | [puros-provider-spotify](https://github.com/jacobbvfx/puros-provider-spotify) | [Latest](https://github.com/jacobbvfx/puros-provider-spotify/releases/latest) |
| TIDAL | [@jacobbvfx](https://github.com/jacobbvfx) | Subscription | Catalog, library and lossless playback (FLAC, up to the quality your plan allows). Apple Silicon only. | [puros-provider-tidal](https://github.com/jacobbvfx/puros-provider-tidal) | [Latest](https://github.com/jacobbvfx/puros-provider-tidal/releases/latest) |
| YouTube Music | [@jacobbvfx](https://github.com/jacobbvfx) | Google account | Connects with a pasted browser cookie. Original AAC or Opus streams through yt-dlp; Opus plays while it downloads. | [puros-provider-youtube-music](https://github.com/jacobbvfx/puros-provider-youtube-music) | [Latest](https://github.com/jacobbvfx/puros-provider-youtube-music/releases/latest) |

The "Latest" links point to each repository's newest build. Builds that are not signed by a publisher key show an "unsigned, publisher unverified" warning in Puros.

## Adding a provider

Open a pull request that adds a row to [Unofficial providers](#unofficial-providers). A provider is listed when:

- its source code is public, under an open-source license, and built with the [Provider SDK](https://github.com/purosapp/puros-provider-sdk);
- installable ZIPs are published as GitHub releases, ideally built by CI from the tagged source;
- its README explains what it does, which account it needs, what it stores, and which helper programs and licenses it bundles.

Being listed is not a review or an endorsement. Entries that stop working, disappear or turn out to be harmful are removed.
