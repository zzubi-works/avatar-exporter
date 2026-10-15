# Curious Bobby VPM repository

Files to publish (GitHub repository `zzubi-works/avatar-exporter`, no push is done by the build):

1. `index.json` → the repository's `main` branch root. Listing URL: `https://raw.githubusercontent.com/zzubi-works/avatar-exporter/main/index.json`
   Users add it in ALCOM / VCC: `vcc://vpm/addRepo?url=https://raw.githubusercontent.com/zzubi-works/avatar-exporter/main/index.json`
2. `com.curiousbobby.avatar-exporter-1.0.6.zip` → a GitHub release tagged `v1.0.6` (asset name unchanged). The index points at
   `https://github.com/zzubi-works/avatar-exporter/releases/download/v1.0.6/com.curiousbobby.avatar-exporter-1.0.6.zip` and carries its SHA-256 (`19928459d34ed6e6d4c79b332a01e2c0a72144d96442bbed0a1f7dbe76bbfbbd`), so ALCOM / VCC verify the download.

Updates: build the next version (tools/pack_commercial.py merges it into this index.json, newest first), publish the new zip as a
release `v<version>` and replace index.json on `main`. ALCOM / VCC show the update in the project's package list.

Local check before publishing: `python tools/vpm_local_test.py` serves this folder on localhost, points a copy of the index at it
and installs the package into a scratch project with the VPM CLI.
