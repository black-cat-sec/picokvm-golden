# PicoKVM golden image

Hardened System image for the Luckfox PicoKVM, used by Black Cat Security / Lightspeed Remote Access. Every KVM
runs the same image. Built and verified by a private pipeline; releases here are read-only downloads.

## Install (on the KVM)
*Settings → Version* → Update source **Custom** → base URL

    https://github.com/black-cat-sec/picokvm-golden/releases/latest/download/

→ *Save* → *Check for Updates* → *Update*. The KVM's own updater fetches `version.txt`, `update_system.zip` and the
`.sha256` files relative to that URL and installs to its inactive A/B slot.

## Releases
Only the **Latest** release is for the fleet (that is what `releases/latest/download/` serves). Releases marked
**Pre-release** are under test on the test unit and must not be installed anywhere else.

## What's in it
Vendor Luckfox System 0.1.8 with: root-owned rootfs; telnet removed; SSH key-only (management public key) with the root
password locked; once a Cloudflare tunnel token is set, the web UI is bound to localhost and the LAN ports are
firewalled (IPv4 + IPv6); IPv6 off; vendor update sources disabled; the KVM app pinned. No secrets: no passwords, no
private keys, no tunnel tokens — each KVM receives its own token after install.

Each release lists the sha256 of every file.
