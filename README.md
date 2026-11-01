# SufyanTreble

A lightweight custom GSI for the **Realme Note 50** (4 GB / 64 GB, Unisoc T612), built by customizing a bare Android 15 AOSP GSI — no feature bloat, just what the phone needs.

**Made by Abu Sufyan**

**Version: 1.0** (Android 15, arm64, A/B)

## What's inside

- **Bare Android 15 base** — ponces' TrebleDroid AOSP GSI (the same device-fix foundation the big custom ROMs stand on), with 17 useless packages removed (~94 MB): extra clock packs, print stack, screensaver/photo-table extras, and Qualcomm/MediaTek-only parts that do nothing on this phone
- **Play Store built in** — a light Google pack (MindTheGapps core): Play Services + Play Store + the small sync pieces, nothing else from Google
- **Play Integrity Fix + Tricky Store setup** — the official module zips (Tricky Store, Tricky Addon by KOWX712, PlayIntegrityFork), a pre-seeded target list and a fingerprint config are carried inside the ROM at `/system/etc/sufyan/` with a plain-language README. They activate after a clean Magisk root, in the order written there. **Honest note:** no keybox is bundled — DEVICE/STRONG integrity depends on a valid keybox, which no ROM can guarantee
- **Gold boot animation** — SufyanTreble's own, drawn at 2x and fitted to the Note 50's 720×1600 screen
- **Version check** — Settings → About shows *SufyanTreble 1.0*
- Everything a GSI needs stays untouched: telephony/IMS, Treble settings, DSU support

## Download (v1.0)

| File | Size | SHA-256 |
|---|---|---|
| `SufyanTreble-v1.0-arm64-ab.img.xz` | 890,648,352 B (~0.89 GB) | `2595620d556775ec21bb5fa3b57af34a5da19db75a0d5d963c895f8599060e05` |
| `SufyanTreble-v1.0-arm64-ab.img` (uncompressed) | 2,892,152,832 B (~2.89 GB) | `62962b5fcbbd83bece765cc4d1c44e3333af9aaeac187b6f71ab0008fa744a5f` |

**Download:** [SufyanTreble-v1.0-arm64-ab.img.xz](https://github.com/abu-pro/SufyanTreble/releases/download/v1.0/SufyanTreble-v1.0-arm64-ab.img.xz) — from the [v1.0 release](https://github.com/abu-pro/SufyanTreble/releases/tag/v1.0).

## Trying it safely — DSU first

SufyanTreble is a GSI: it replaces only the **system** partition. The safe first test is **DSU** (boot it temporarily, e.g. with DSU Sideloader — a reboot returns to your current ROM untouched). Only flash it for real (fastbootd, system partition) once the DSU test passes the checklist: calls on 4G/auto mode, SMS, Wi-Fi, camera, fingerprint, Play Store sign-in, and speed/RAM compared with your old ROM.

**Before any switch:** take a full WhatsApp backup and keep your stock firmware safe.

## Known honest limits

- VoLTE on Unisoc GSIs is not guaranteed — if incoming calls fail on 4G-only mode, use the auto (4G/3G/2G) network mode and the Treble app's IMS options
- Play Integrity verdicts depend on external, revocable pieces (keybox/fingerprint) — see the note above
- Security patch of the base: 2025-05-05

## Credits

- **Made by Abu Sufyan** — selection, debloat, integration, branding
- Base GSI: [ponces](https://github.com/ponces/treble_aosp) / TrebleDroid & phhusson (Apache/GPL components as in the base)
- Google pack: [MindTheGapps](https://github.com/MindTheGapps)
- Bundled setup zips (unmodified, official releases): [Tricky Store](https://github.com/5ec1cff/TrickyStore), [Tricky Addon](https://github.com/KOWX712/Tricky-Addon-Update-Target-List), [PlayIntegrityFork](https://github.com/osm0sis/PlayIntegrityFork)
