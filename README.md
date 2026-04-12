# ArGram – Galaxy-Themed Telegram Desktop

ArGram is a custom fork of [Telegram Desktop][telegram_desktop] with a galaxy visual identity: deep navy background, violet accents, and cyan highlights — built on the official [Telegram API][telegram_api] and [MTProto][telegram_proto] secure protocol.

## What's Different from Telegram Desktop

| Feature | Telegram Desktop | ArGram |
|---|---|---|
| Theme | Light / Dark | Galaxy dark (navy + violet + cyan) |
| Icon | Official airplane | Neon gradient ring + airplane |
| Premium | Subscription required | Unlocked client-side |
| Stars | Purchase required | 999 999 stars, no purchase flow |
| Default wallpaper | Static | Animated galaxy gradient |

### Galaxy Theme

Colors:
- Background: `#0D0D1A` (deep navy)
- Accent: `#7B2FFF` (violet)
- Highlight: `#00D4FF` (cyan)

All built-in themes are replaced with the Galaxy palette. The default wallpaper uses an animated gradient rotation effect.

## Supported Systems

Same as upstream Telegram Desktop:

- Windows 7 and above (64-bit / 32-bit)
- macOS 10.13 and above
- Linux (static 64-bit build, Snap, Flatpak)

## Build Instructions

### Prerequisites

The build system expects this directory layout:

```
L:\Telegram\
L:\Telegram\tdesktop\       ← this repository
L:\Telegram\Libraries\      ← 32-bit dependencies (Linux/macOS)
L:\Telegram\win64\Libraries\ ← 64-bit dependencies (Windows)
L:\Telegram\ThirdParty\     ← build tools
```

### Build

From the repository root:

```bash
cmake --build out --config Debug --target Telegram
```

The executable will be at `out/Debug/Telegram.exe`.

> Always use Debug builds. Release is extremely heavy and not needed for local testing.

### Platform Notes

**Windows** — requires Visual Studio 2022. Run from the matching Native Tools Command Prompt (`x64` / `x86` / `ARM64`).

**macOS** — requires Xcode. Set `QT` env var: `export QT=6.8`

**Linux** — dependencies in `../Libraries`. Set `QT` if needed.

## Third-Party Libraries

ArGram inherits all third-party dependencies from Telegram Desktop, including Qt 6, OpenSSL 3, WebRTC, FFmpeg, OpenAL Soft, and others. See [Telegram Desktop's README][tdesktop_repo] for the full list and their respective licenses.

## License

Source code is published under GPLv3 with OpenSSL exception — see [LICENSE][license].

[//]: # (LINKS)
[telegram_desktop]: https://desktop.telegram.org
[telegram_api]: https://core.telegram.org
[telegram_proto]: https://core.telegram.org/mtproto
[tdesktop_repo]: https://github.com/telegramdesktop/tdesktop
[license]: LICENSE
