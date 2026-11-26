# AGT Browser add-on

AGT Browser is a full Chromium 157 browser packaged as an AGT add-on
(id `agt-browser`): it runs headed on the agent's own XFCE desktop or
headless, on the phone.

This repo holds the add-on's authored source files:

- `addon.json` — the add-on manifest
- `bin/agt-browser` — the launcher: resolves the add-on root, sets the
  library path, bridges the X socket (Chromium's libxcb has the build
  prefix baked in), exports the package fontconfig, applies
  `etc/chromium/*.conf` flags, and execs the browser
- `etc/chromium/default.conf` — default Chromium flags
- `etc/fonts/fonts.conf` + `etc/fonts/conf.d/` — the package's own
  fontconfig (DejaVu aliases for the generic families)

The binary payload (`lib/`, `share/fonts`, locales) is built from the
Chromium stack and ships in the release zip, not in this tree.

## Install

Download `agt-browser-<version>.zip` from the Releases page and
install it as an AGT add-on with its sha256 pin, e.g. through
`agt_jobs.py addon-install --url <zip-url> --sha256 <pin>`.

Version 0.1.1 sha256:
cf9142d294208258e5ef53ba6d0d1cb511bfc4fc02aa0e5fa10f8f28cbcc3d24

## Known limits

- Ships DejaVu fonts only: Latin, Cyrillic and Arabic scripts render;
  CJK text renders as boxes until a CJK font is added.
