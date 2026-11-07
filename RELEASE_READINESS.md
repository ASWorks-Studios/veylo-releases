# Veylo 0.11.4 — free preview release scope

Developed by ASWorks. Distribution: https://asworks.studio/product/veylo

This is a free Windows x64 preview with an unsigned executable and installer. It is not a certified Microsoft Store release or a generally production-qualified application. `production_qualified=false` remains intentional. Windows 11 x64 is the initial preview target; Windows 10 1809+ meets the installer minimum but has not completed independent qualification. Android, macOS, Linux and Windows ARM are not supported releases.

## Changes in 0.11.4

- Add Remove saved key in Preferences. It cancels active operations, clears the current provider connection/check and removes only the current DPAPI credential. Legacy files and other settings remain untouched.
- Add official download, help and privacy links in About and installer metadata.
- Explain free app access separately from Google account usage costs; preserve intentional bring-your-own-key recognition.
- Refresh customer documentation, licence attribution and the direct ASWorks publication process.

## Verification and publication

Run formatting, Clippy, tests, dependency audit, static-runtime build, package verification and isolated installer checks for the exact source revision. Bind the final artifact hashes to malware-scan evidence before ASWorks approval. Source code, development tools, keys, profiles and recordings are excluded from packages. Current execution evidence belongs in ASWorks's publication record; older audit reports describe their original versions and hashes.

The owner authorized a free preview for direct ASWorks distribution. No usable signing identity is currently available: the download page must display unsigned status and known limitations. Do not imply a checksum is publisher signing or advise disabling security software. Code signing and broader device/real speech qualification remain work for a later release. Direct ASWorks distribution does not require Microsoft Store certification; any future store submission has its own requirements.

## User requirements and limits

Internet, microphone permission and the user's Gemini key with model access/quota are required. Google processes recognition audio and may charge the user's account. No ASWorks payment, card, licence activation or mandatory ASWorks login is needed for this preview. Future paid editions require a separate voluntary choice and do not revoke the licence granted with this version.

Recognition can be inaccurate. Automatic insertion is limited to verified fields; unsupported, multiline, oversized, interrupted and recovered results use review/copy. Commands are a defined set of dictation/text-editing actions, not arbitrary computer control. Sessions are limited to 20 minutes. Updates are manual through the official download page, with the same installer identity and retained user data.

Clean-device, Windows 10, accessibility, Bluetooth, sleep/resume, editor and representative multilingual testing remain incomplete unless a later evidence record explicitly establishes them. No universal compatibility, zero-bug, guaranteed latency or accuracy claim is made.
