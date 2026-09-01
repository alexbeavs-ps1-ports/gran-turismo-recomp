# Gran Turismo feasibility

## Current result

The source-only setup host binds the owned USA Rev 1 boot program
`SCUS_941.94` to PSXRecomp `8b4e0900`. The disc probe found a 141,312-byte
program with entry point `0x800317B8` and SHA-256
`92ED13CEA4096BC1EACFE26A20B3E6D6F22DC5AE909F13DA75D9EDA46949691B`.

This source tree contains no disc image, retail BIOS, generated retail code,
save, capture, decompilation output, or private path. It does not claim
gameplay or release status.

## Known boundary

The boot program is not the complete game program surface. Gran Turismo loads
additional programs and uses nonstandard IKI movie data. The stable lane needs
an explicit program lifecycle and media gate before it can claim more than a
setup host. Analog controller mode also remains explicit device state.

Experimental decompilation and function overrides remain outside this source.
They can enter stable source only after equivalence, deterministic fallback,
and removal or acceptance gates pass.

## Package source gates

The release workflow rejects a mismatch between the build, package, and
deferred-relaunch executable names. The package wrapper treats
`launcher_assets` as optional and stages it only when the clean source
contains a package asset.

## Next gate

Build the setup host from a clean checkout. Package the exact source-only ZIP.
Then generate from the owned disc in an ignored directory and run a hidden
startup test. Alex must complete the visible manual route before any release.
