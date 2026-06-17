# Deprecated overlays — historical reference only

These are the original NextThingCo CHIP DIP overlays (written for the 4.4
NextThing vendor kernel) together with the EEPROM-PID symlink names that used
to reference them (`dip-<vid>-<pid>[-<subvariant>]`).

**Nothing here is built or shipped.** The Makefile only globs `firmware/*.dts`,
`firmware/early/*.dts` and `samples/*.dts`, so `firmware/deprecated/` is never
compiled into a `.dtbo` and never lands in the package. The files are kept
purely to document the original DIP definitions and the historical naming.

The maintained, mainline (Linux 6.12 / `sun5i-r8-chip`) replacements live in
`../early` under the `x-chip-*` convention:

| legacy symlink            | legacy source        | PID | mainline replacement   |
|---------------------------|----------------------|-----|------------------------|
| `dip-9d011a-1` / `-1-49`  | `dip-pocket-v73.dts` | 1   | `x-chip-pocketchip`    |
| `dip-9d011a-1-48`         | `dip-pocket-v72.dts` | 1*  | (keymap -48/v72 — not yet ported) |
| `dip-9d011a-2`            | `dip-vga.dts`        | 2   | `x-chip-dip-vga`       |
| `dip-9d011a-3`            | `dip-hdmi.dts`       | 3   | `x-chip-dip-hdmi`      |

\* `-48`/`-49` are the two PocketCHIP keymap revisions (v72/v73), distinguished
by the EEPROM product-version byte, not by PID. See the `dt-overlays-dip`
project notes.
