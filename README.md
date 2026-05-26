This repo includes an OpenWrt kernel module package for https://github.com/frankcrawford/it87

Requirements:
  * x86_64
  * OpenWrt 25.12.4+

Installation:
  1. Download apk from github release
  2. Ensure the old `kmod-hwmon-it87` is uninstalled (`apk del kmod-hwmon-it87`)
  3. `apk add --allow-untrusted /path/to/downloaded/package.apk`
