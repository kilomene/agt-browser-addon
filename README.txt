AGT Browser 0.1.1 binary distribution
=====================================

The add-on zip is split into parts to fit GitHub file limits.

Rebuild the zip:
  cat agt-browser-0.1.1.zip.part-* > agt-browser-0.1.1.zip

Verify it (must match exactly):
  sha256sum agt-browser-0.1.1.zip
  -> cf9142d294208258e5ef53ba6d0d1cb511bfc4fc02aa0e5fa10f8f28cbcc3d24

Then install it as an AGT add-on with that sha256 as the pin.
Per-part hashes are in SHA256SUMS.txt.
