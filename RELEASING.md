# Release files and versioning

## Release files

For a new installation or a manual upgrade, download **`VibeWire-<version>-windows-x64-setup.exe`** from the [public Stable release](https://github.com/oofitsnathaniel/vibewire/releases/latest). The other files serve these purposes.

| File | Purpose |
| --- | --- |
| `RELEASE-NOTES.md` | The release notes included in the update workflow. The manifest includes their expected SHA-256. |
| `SHA256SUMS.txt` | The expected SHA-256 fingerprints. Use it to compare the installer you downloaded with the published copy. |
| `update-manifest-win-x64.json` | The Windows Stable updater’s metadata, including the release version, installer name, size, and SHA-256. |
| `update-manifest-win-x64.json.sig` | The detached publisher signature for the manifest. The updater checks it with its built-in public key. |
| GitHub’s **Source code (zip)** / **Source code (tar.gz)** | Automatic archives of the tagged repository. The 1.0.0 archives contain the README and wordmark. Use the setup executable to install Vibe Wire. |

To compare a manual 1.0.0 download, open PowerShell in the folder that contains the installer and run:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\VibeWire-1.0.0-windows-x64-setup.exe
```

Compare the full hash with the installer line in `SHA256SUMS.txt` from the same release.

## Versioning policy

- Give every change to published installer bytes a new version and Git tag. Use a patch version such as `1.0.1` for compatible fixes.
- Publish the installer, release notes, checksums, and matching signed update metadata together. Verify the actual download and the upgrade from the prior release before announcing it.
- Keep the published installer, tag, and signed files for earlier versions intact. Changes to the GitHub release description can clarify instructions independently of the attached files.
- Use the existing channel-specific signature and manifest files for Stable and Private Beta. Stable remains the public default. Private Beta remains access-controlled.

The 1.0.0 installer was refreshed once to enable bug reporting. Users who installed the first 1.0.0 build can rerun the current installer manually. Future installer fixes will have a new version so the updater can offer them.
