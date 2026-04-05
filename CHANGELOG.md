> `Changelog:`
> - All significant changes to this project will be documented here.
---

> [3.5.0]
>
> - Changed the structure of `README.md` for a better impression.
> - Updated `README.md` description and feature list.
> - Updated `customize.sh` and `verify.sh` for better future performance.
> - Improved `detect_root_all` to match latest root manager variants.
> - Improved `set_donate_link` timezone detection with multiple fallbacks.
> - Fixed `local var=$(...)` declarations for better shell compatibility.
> - Fixed `post_install_actions` missing `NAME_MODULE` definition.
> - Fixed `post-fs-data.sh` missing closing quote on `MODDIR`.
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
> - Moved all `resetprop` calls to `post-fs-data.sh` for earlier application.
---

> [2.5.0]
>
> - License Changes.
> - Changed the structure of `README.md` for a better impression.
> - Changed the module description to be more professional.
> - Updated `customize.sh and verify.sh` for better future performance.
> - Updated `uninstall.sh` to be cleaner for removing modules.
> - Removed some unnecessary code in `service.sh` and updated it to be more effective.
> - Added backup and restore functionality for GPS configuration files.
> - Added sensor batching configuration for accelerometer and gyroscope to improve dead reckoning accuracy.
> - Enabled LPP (LTE Positioning Protocol) and geofencing features for better location accuracy and responsiveness.
> - Sorted all parameters A-Z in configuration files for better maintainability.
> - Cleaned up the previous Changelog to make it cleaner when reading the changelog.
> - And there are many more improvements and updates or other fixes.
---