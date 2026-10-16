# Curious Bobby VPM repository

Files to publish (GitHub repository `zzubi-works/avatar-exporter`, no push is done by the build):

1. `index.json` → the repository's `main` branch root. Listing URL: `https://raw.githubusercontent.com/zzubi-works/avatar-exporter/main/index.json`
   Users add it in ALCOM / VCC: `vcc://vpm/addRepo?url=https://raw.githubusercontent.com/zzubi-works/avatar-exporter/main/index.json`
2. `com.curiousbobby.avatar-exporter-1.0.7.zip` → a GitHub release tagged `v1.0.7` (asset name unchanged). The index points at
   `https://github.com/zzubi-works/avatar-exporter/releases/download/v1.0.7/com.curiousbobby.avatar-exporter-1.0.7.zip` and carries its SHA-256 (`5ccab6eceafcc8d4d964fbeba4602eb3e2bf825c0f9eea15c77ad53db29f789d`), so ALCOM / VCC verify the download.

Updates: build the next version (tools/pack_commercial.py merges it into this index.json, newest first), publish the new zip as a
release `v<version>` and replace index.json on `main`. ALCOM / VCC show the update in the project's package list.

Local check before publishing: `python tools/vpm_local_test.py` serves this folder on localhost, points a copy of the index at it
and installs the package into a scratch project with the VPM CLI.
