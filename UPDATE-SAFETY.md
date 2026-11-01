# Updates and existing saves

The Store release uses title/install folder PPSA99731. An older manually installed PhazonPrime may use PPSA99896. Those are separate PS5 titles: installing one does not update the other or automatically transfer its saves. Never delete the old installation to work around this difference before a verified backup and save migration.

Native saves and autosaves are inside the installed application's userdata directory. On an old PPSA99896 installation this is /data/homebrew/PPSA99896/userdata; the Store title uses /data/homebrew/PPSA99731/userdata. Keep the complete userdata directory, including both native-pal-state-v2 generations, native-pal-auto-v1 files, language/settings and AxioDL configuration. Do not mix TEST PPSA99733 data into either title.

For an existing managed Store installation, choose **Quick update** (the overwrite/keep-existing-files mode) when available. Our release archives contain no userdata, saves or ISO, so a file overlay leaves those files intact. A clean replacement is different: the reviewed ProsperoStore implementation moves the previous entire application to its previous folder, normally /data/prosperostore/previous/PPSA99731 on internal storage. Its saves may remain there while the newly installed application looks empty. A later update can replace that previous folder, so it is not a durable backup. Store versions can differ; verify the displayed update mode and destination rather than assuming preservation.

Before updating: make a separate verified backup of the entire userdata directory and your own ISO; keep that backup outside the install and Store work folders. If the file manager cannot read private save files, do not change permissions or format them. The existing owner-export mode can make a checked archive using the application's own access, exiting before the engine/settings load. Its export must be copied to a private backup and protected again. A one-time transfer from PPSA99896 to PPSA99731 must validate that export and restore only into an empty destination; it is not performed merely by downloading this release.

Do not promise that an external installer preserves every file. The safeguards are a verified independent backup, matching title identity, an overlay update, and a checked restore when migrating. No actual save data is included in this repository or release.

Reviewed installer source: https://github.com/darkxex/ProsperoStore/blob/main/src/install/transaction.cpp
