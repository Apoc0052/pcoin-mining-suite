# PCoin Windows RandomX Build Verification Report

Date: 2026-10-06
Maintainer: Apoc0052
Upstream source: pars5555/pcoin
Upstream version: PCoin Core v29.4.0

## Purpose

This report documents an independently built Windows x64 PCoin Core daemon with RandomX proof-of-work support, together with a matching Windows RPC client.

This is a community build and is **not an official PCoin Core release**.

## Build environment

- Windows x64
- Visual Studio 18 Community
- MSVC 14.51.36231
- CMake 4.3.1-msvc1
- Ninja 1.13.2
- Windows SDK 22621 tools for resource/manifest processing
- C++20
- RelWithDebInfo
- MSVC debug information format: /Z7

## Important toolchain finding

During the build, MSVC compilation intermittently terminated with Windows access-violation code 0xC0000005 when generated compile-PDB handling used /Zi.

The generated build was stabilized by changing generated compile flags from /Zi to /Z7 and removing per-target compile-PDB settings. This does not change the PCoin source implementation; it changes the Windows build configuration used for this test.

The Windows SDK 26100 mt.exe was also independently observed to terminate with 0xC0000005 during manifest processing. Windows SDK 22621 mt.exe completed the equivalent manifest test successfully and was used for the final build.

## Build results

### PCoin Core daemon

- bitcoind.exe: built successfully
- RandomX: compiled and linked
- RandomX section present in the final executable
- RandomX proof-of-work verification initialized successfully at runtime

### RPC client

- bitcoin-cli.exe: built successfully
- Version test: PCoin Core RPC client v29.4.0
- Exit code: 0

## Real-chain verification

A copy of the PCoin SOLO server blockchain data was used for a non-destructive test.

The new Windows daemon loaded the real PCoin main chain and reported:

- Chain: main
- Height: 11115
- Headers: 11115
- Best block: bac0d66ef51b912306cd55b9f180d1ae0057936b77c6bd32c0396dc9d308a63f
- Difficulty: 0.1511883284963527
- Verification progress: 1.0
- Initial block download: false
- Pruned: false
- Warnings: none

The daemon verified the last six blocks successfully with no coin-database inconsistencies.

A separately built bitcoin-cli.exe queried the same daemon over RPC and returned the same blockchain information with exit code 0.

## Clean deployment verification

A clean deployment directory was created containing only:

- bitcoind.exe
- bitcoin-cli.exe
- event_core.dll
- event_extra.dll
- COPYING

The clean deployment was tested from its own directory with a fresh temporary datadir. It initialized RandomX, started its network/RPC threads, reached "Done loading", and shut down cleanly.

## Release artifact

File:

PCoin-RandomX-Windows-Final-2026-10-06.zip

Size:

6,094,836 bytes

SHA-256:

6E7BB1ADC21DF554E7828A566B4EC75016EC37D02A2C66F37326BE91360AD290

The ZIP was extracted and its five expected files were verified.

## Scope and status

This verification establishes that the community-built Windows x64 PCoin Core v29.4.0 daemon with RandomX support can:

1. Start independently.
2. Initialize RandomX.
3. Load the actual PCoin main chain.
4. Verify existing PCoin blocks.
5. Serve RPC requests.
6. Be queried successfully by the matching bitcoin-cli.exe.
7. Run from a clean deployment directory without the original build tree.

This report does not claim official PCoin endorsement, release status, or upstream acceptance. It is intended to provide reproducible evidence for review by the PCoin developers/community.

## Source and licensing

The PCoin source remains subject to its upstream license and repository terms. Third-party components retain their respective licenses.

For official upstream source and project information, see the pars5555/pcoin repository and PCoin project website.
