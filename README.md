# SufyanTreble

A lightweight custom GSI for the **Realme Note 50** (4 GB / 64 GB, Unisoc T612), built by customizing a bare Android 15 AOSP GSI — no feature bloat, just what the phone needs.

**Made by Abu Sufyan**

**Version: 1.0** (Android 15, arm64, A/B)

## What's inside

- **Bare Android 15 base** — ponces' TrebleDroid AOSP GSI (the same device-fix foundation the big custom ROMs stand on), with 17 useless packages removed (~94 MB): extra clock packs, print stack, screensaver/photo-table extras, and Qualcomm/MediaTek-only parts that do nothing on this phone
- **Play Store built in** — a light Google pack (MindTheGapps core): Play Services + Play Store + the small sync pieces, nothing else from Google
- **Play Integrity Fix + Tricky Store setup** — the official module zips (Tricky Store, Tricky Addon by KOWX712, PlayIntegrityFork), a pre-seeded target list and a fingerprint config are carried inside the ROM at `/system/etc/sufyan/` with a plain-language README. They activate after a clean Magisk root, in the order written there. **Honest note:** no keybox is bundled — DEVICE/STRONG integrity depends on a valid keybox, which no ROM can guarantee
- **Gold boot animation** — SufyanTreble's own, drawn at 2x and fitted to the Note 50's 720×1600 screen
- **Version check** — Settings → About shows *SufyanTreble 1.1*
- Everything a GSI needs stays untouched: telephony/IMS, Treble settings, DSU support

## Download (v1.1 — latest)

**New in v1.1:** Google SetupWizard is now baked in, so the first-boot Google setup flow runs properly (v1.0 could stall before the home screen and sign-in); new "SUFYAN OS" gold boot animation with a gentle breathing glow. SIM/telephony is unchanged from v1.0 — on the test phone the SIMs got no service on this base; check your IMEI/SIM status first in the DSU test.

| File | Size | SHA-256 |
|---|---|---|
| `SufyanTreble-v1.1-arm64-ab.img.xz` | 842,438,512 B (~0.84 GB) | `a8850d8a53ad8f885c877002d2b49b5e5f4a36a11c57e94fb0eacc87ebbaafdb` |
| `SufyanTreble-v1.1-arm64-ab.img` (uncompressed) | 2,892,152,832 B (~2.89 GB) | `4d13fcae89df03cf1fd3a1490bc13c37e2061c1121b2ab140f9f64d7df83d62b` |

**Download:** [SufyanTreble-v1.1-arm64-ab.img.xz](https://github.com/abu-pro/SufyanTreble/releases/download/v1.1/SufyanTreble-v1.1-arm64-ab.img.xz) — from the [v1.1 release](https://github.com/abu-pro/SufyanTreble/releases/tag/v1.1). The older [v1.0 release](https://github.com/abu-pro/SufyanTreble/releases/tag/v1.0) stays available.

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
