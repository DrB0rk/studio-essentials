# Studio Essentials

Internal distribution for the StudioSatellite project.

**Install page**: https://drb0rk.github.io/studio-essentials/

## Layout

| Path | Contents |
|------|----------|
| `app/` | iOS app — `StudioSattelite.ipa` + itms-services manifest |
| `firmware/` | Latest AMS7 core gateway firmware (`ams7_esp32.bin`) |
| `installers/` | Desktop installers — `AMS7-Studio-latest-setup.exe` |
| `questionnaires/` | English / Dutch questionnaire JSON |

## Questionnaire URLs used by the iPad app

- `https://drb0rk.github.io/studio-essentials/questionnaires/questionnaires.en.json`
- `https://drb0rk.github.io/studio-essentials/questionnaires/questionnaires.nl.json`

Both are configurable in the iPad app's Settings → Questionnaire URLs.

## iPad install requirements

- Device UDID must be registered on Apple Developer team `L34UB8AH3J`
- Open the install page in **Safari** on the target iPad
- After install: Settings → General → VPN & Device Management → trust the developer profile

## Adding files

Drop new files into the appropriate folder, commit, push. Pages rebuilds in ~30s.

When updating the IPA:

- Replace `app/StudioSattelite.ipa` with the new build (same filename avoids iOS caching)
- The `app/manifest.plist` references the IPA by name — no edit needed if the filename stays the same
- iOS aggressively caches the manifest; if users report the wrong version, rename the new IPA (e.g. `StudioSattelite-v2.ipa`) and update both the `url` in `manifest.plist` and any links in `index.html`