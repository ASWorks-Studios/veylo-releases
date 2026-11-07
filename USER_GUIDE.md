# Veylo 0.11 — Windows setup and recovery

This build is an unsigned development preview for Windows 10 (1809 or newer) and Windows 11, x64. Internet, a working microphone and your own Gemini API key with access/quota for the selected model are required. No additional development tools or speech-model downloads are required. Windows ARM and other operating systems have not been qualified.

## First installation

1. Run the Veylo installer under your Windows account. Installation is per user and does not require administrator rights. The portable ZIP can instead be extracted into a stable folder before opening `veylo.exe`.
2. In Preferences → Voice & writing, select **Use fast dictation setup** if you want live recognition and automatic typing. This enables upload while speaking, a 20-second idle connection and verified field insertion. It does not enable history or recording at sign-in.
3. Enter your own Gemini key, click **Save key**, then **Test Gemini connection**. The test verifies the selected model without uploading audio. Changing the recognition mode requires another test during setup.
4. Choose **Windows default** or a microphone, run the five-second local microphone test and speak. The test discards audio without uploading it. Check Windows microphone permission, input level and mute if no signal is detected. Veylo cannot grant Windows permission itself.
5. Optionally enable **Start Veylo when I sign in to Windows**, then finish setup. Windows Startup Apps can override this registration. For a portable copy, moving the executable requires updating this preference.
6. Focus an editable field in another app. Press **Ctrl+Space**, speak, then press it again. Review the output before sending it. Recording started from the workspace or tray stays in Veylo for review.

Keys are encrypted for the current Windows account; copying someone else's profile does not provision your own account. Never share your key or profile folder with the installer.

## Daily use

| Action | Default shortcut |
| --- | --- |
| Toggle dictation | Ctrl+Space |
| Hold to dictate | Ctrl+Alt+Space |
| Open workspace | F9 |
| Insert last result into current verified field | Ctrl+Alt+V |
| Command mode | Ctrl+Shift+Space |
| Apply reviewed command edit | Ctrl+Shift+R |
| Undo last verified command edit | Ctrl+Alt+Z |
| Capture selection without microphone | Ctrl+Shift+E |
| Cancel active work | Escape |

Preferences shows the active bindings and registration status. Occupied startup shortcuts try Ctrl+Alt+F1–F8 and then Ctrl+Shift+F1–F8, in action order; if all choices fail, other actions remain active. Choose a different chord for unavailable actions. A particular shortcut cannot be guaranteed free on every device. Escape can also conflict; use the Cancel control when it does.

Closing the window keeps Veylo and its shortcuts in the tray. Quit from the tray to stop it. With sign-in launch enabled it starts in the tray after setup; recording always requires an explicit action. A failed tray initialization keeps the window accessible and closing it quits. Opening the app again restores the existing workspace.

## Accuracy and repetition

Verbatim is the conservative default. Optional **Smart live formatting** asks Gemini to resolve spoken corrections, fillers and restarts without a second rewrite request. It can change wording and remove intentional repeated sentences. Keep Smart off when exact repetition matters. Review names, numbers, negations, Hindi/Hinglish and intended repetition before relying on it. Original displays the provider's output, including Smart edits; it is not separately raw audio transcription. Local processing never blindly removes repeated words or sentences. Personal vocabulary and explicit spelling corrections help names and specialist terms.

## When something needs attention

- **No audio:** select or refresh the microphone and run the local test. Reconnect a removed device, or choose Windows default. Check Windows microphone access and mute yourself.
- **Processing seems stuck:** the workspace shows elapsed time. Escape cancels; short recordings stop waiting after 45 seconds and longer recordings after 195 seconds. Any available retry audio remains in memory for up to 120 seconds. The pill closes on completion, cancellation or failure. Reopen the workspace with F9 to inspect the status.
- **No connection:** check internet, key, model access, quota and billing. Retest the connection. Recorded audio is kept in memory for a manual retry for up to 120 seconds after a recognition failure; exit, cancel or a new recording discards it.
- **Words appear only in Veylo:** enable automatic insertion, start with a shortcut while the intended field is focused, and keep that field active. Password/read-only/elevated or unsupported editors may reject insertion. Veylo shows a reason and keeps the transcript for copy. It does not elevate itself to bypass an editor's protection.
- **Long or multiline text:** sessions allow up to 20 minutes. Automatic typing is limited to a single line and 8,000 UTF-16 units. Larger, multiline or interrupted/recovered results require review and copy. This avoids treating Enter as a send/execute action in another app.
- **Partial input or timeout:** inspect the destination before using Insert last or Copy; retrying the whole result may duplicate text already inserted. Input submission is not proof that every editor rendered all characters.
- **Interrupted microphone/connection:** incomplete audio/text is marked for review and cannot execute commands automatically. Live recovery may resend audio and consume more quota.
- **Damaged/newer settings:** Veylo preserves the file and disables writes. Keep a backup before recovery; do not delete keys as a troubleshooting step.
- **History:** saving is opt-in, local and not encrypted by Veylo. Turning it off does not delete old entries. Clear history explicitly if needed. With history off, current words and drafts do not survive quitting or a crash; copy important results before updating.

## Updates, uninstall and sharing

Share only the versioned installer or ZIP and its `.sha256` file. All payload hashes are in `package-manifest.json`. SHA-256 detects corruption against a trusted checksum; it is not publisher signing. This preview has no automatic updater. Close Veylo and install a newer verified release; save current words first. Settings and the DPAPI key are retained across upgrades. Uninstall removes app binaries/registered shortcuts but preserves `%LOCALAPPDATA%\Veylo\v4` user data. Any old plaintext imported key remains owner-managed.

Official downloads: https://asworks.studio/product/veylo. Setup/support: https://asworks.studio/apps/veylo/help. Privacy: https://asworks.studio/apps/veylo/privacy. Contact hello@asworks.studio. This direct ASWorks preview is unsigned; broader qualification and signing remain open. Microsoft Store certification is not required for this channel. See PRODUCTION_READINESS.md and PRIVACY.md in the package.

## Keys and free-preview access
Replace a key using Save key and retest the connection. Remove saved key cancels current operations and removes only the current protected credential; it does not revoke the key at Google or delete a legacy imported file. Revoke compromised keys through Google AI Studio. The preview requires no ASWorks payment, card or activation. Google usage charges may apply; future paid editions are optional separate offers.

