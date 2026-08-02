> `Changelog:`
> - All significant changes to this project will be documented in this file.
---

> [4.5.0]
>
> - Added `persist.gps.qc_nlp_in_use` to `post-fs-data.sh` — enables Qualcomm Network Location Provider for AGPS on supported devices.
> - Added timeout (30 seconds) to GMS wait loop in `service.sh` — prevents infinite hang on non-GMS devices.
> - Added `fstrim` per partition to `uninstall.sh`.
> - Added cache cleanup for dalvik, resource-cache, dropbox, and tombstones to `uninstall.sh`.
> - Added notification after optimization completes in `service.sh`.
> - Changed `detect_root_all` in `customize.sh` — refactored to loop-based format, detection order APatch → KernelSU → Magisk, added `VortexSU`, `Kokoro Mask`, aapt-based spoofed fallback, and generic ksud fallback.
> - Changed `LPP_PROFILE` in `gps.conf` from `0` to `3` — now consistent with `persist.sys.gps.lpp`.
> - Changed `DEBUG_LEVEL` in `gps.conf` from `3` to `0` — reduces log spam and improves battery.
> - Changed `am force-stop com.google.android.gms` in `service.sh` — now checks `pm list packages -s` first to avoid force-stopping system packages.
> - Changed broadcast action in `service.sh` from `com.android.server.LocationManagerService.PROVIDERS_CHANGED` to `android.location.PROVIDERS_CHANGED`.
> - Changed settings order in `service.sh` and `uninstall.sh` — `global` before `secure`.
> - Changed XTRA file cleanup in `service.sh` and `uninstall.sh` — now targets `xtra*.bin` and `*.xtra` only instead of all files.
> - Removed `SKIPUNZIP=1` and `DEBUG=false` from `customize.sh`.
> - Removed `zip=$(clean_path "$zip")` from `extract()` in `verify.sh`.
> - Removed loop `ro.*` resetprop from `post-fs-data.sh` — no longer needed.
> - Removed loop `persist.*` resetprop from `post-fs-data.sh` — replaced with single `persist.sys.gps.lpp` only.
> - Removed loop `ro.*` resetprop cleanup from `uninstall.sh`.
> - Removed loop `persist.*` resetprop cleanup from `uninstall.sh` — replaced with single `persist.sys.gps.lpp` only.
> - Removed `find -type f -delete` on entire `/data/misc/location` — replaced with targeted XTRA file cleanup in `service.sh` and `uninstall.sh`.
> - Removed section 7 shader/GPU cache cleanup from `uninstall.sh` — too aggressive and unrelated to GPS.
> - Removed `command -v su` fallback from `grant_permission` in `service.sh`.
---

> [3.5.0]
>
> - Added `FolkLite` (`mi.yuki.folk`) detection to `detect_root_all`.
> - Added `AGPS_CONFIG_INJECT`, `AP_CLOCK_PPM`, `AP_TIMESTAMP_UNCERTAINTY` to `gps.conf`.
> - Added `DR_SYNC`, `PPS`, `GNSS_OUTAGE_DURATION`, `MODEM_TYPE` parameters to `gps.conf`.
> - Added `XTRA_SERVER_1/2/3` fallback servers to `gps.conf`.
> - Added `resetprop` existence check before applying properties for cross-device compatibility.
> - Added persist Qualcomm GPS properties via `resetprop -p` in `post-fs-data.sh`.
> - Added high accuracy location mode and provider activation in `service.sh`.
> - Added XTRA data cleanup on boot for fresh ephemeris download.
> - Added force stop and restart GMS after applying new location config.
> - Added `resetprop -d` and `resetprop -p -d` cleanup in `uninstall.sh`.
> - Added `settings delete` for location settings in `uninstall.sh`.
> - Added cache cleanup for GMS and Maps on uninstall.
> - Added numbered comments throughout all scripts for better readability.
> - Changed `README.md` structure and content for a more professional impression.
> - Changed `detect_root_all` to match latest root manager variants.
> - Changed `set_donate_link` timezone detection with multiple fallbacks.
> - Changed all `resetprop` calls moved to `post-fs-data.sh` for earlier application.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Fixed `post-fs-data.sh` missing closing quote on `MODDIR`.
---

> [2.5.0]
>
> - Added backup and restore functionality for GPS configuration files.
> - Added sensor batching configuration for accelerometer and gyroscope to improve dead reckoning accuracy.
> - Added LPP and geofencing features for better location accuracy and responsiveness.
> - Changed license from GNU General Public License to Apache License 2.0.
> - Changed `README.md` structure and content for a more professional impression.
> - Changed module description to be more professional.
> - Changed all parameters in configuration files sorted A-Z for better maintainability.
> - Changed `customize.sh` and `verify.sh` for better future performance.
> - Changed `uninstall.sh` for cleaner module removal.
> - Changed `service.sh` — removed unnecessary code for more effective execution.
---

> [1.0.0]
>
> - Initial release.
---