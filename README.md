# SFH Scripture Backup Mirror

This repo is a backup mirror of SFH's scripture data. It is NOT the live source.

**Live source:** https://cdn.spiritfilledhealth.com/ (Cloudflare R2)

The files in this repo use the original mixed-case underscore naming convention 
(e.g., `01_Genesis.json`, `19_Psalm.json`).

The R2 mirror uses the canonical SFH convention: all-lowercase, hyphenated 
(e.g., `01-genesis.json`, `19-psalms.json`).

## Updating content

1. Edit files in your local `~/sfh-cdn-mirror/` directory (lowercase hyphenated names)
2. Push to R2 via: `rclone sync ~/sfh-cdn-mirror/ r2:sfh-content/ --progress`
3. Bump `cacheVersion` in `loadAllBooks` if existing app installs need to re-fetch
4. Push a new app build if cache version changed

This repo is kept as a backup and version history reference only.
