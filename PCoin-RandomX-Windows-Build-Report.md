# PCoin RandomX Windows Build Report

**Unofficial Windows RandomX build based on PCoin Core v29.4.0**
**Build date:** 2026-10-06
**Maintainer:** Apoc0052
**Status:** Independent community build — unofficial and not endorsed or verified by PCoin

## Binaries

- bitcoind.exe
- bitcoin-cli.exe
- event_core.dll
- event_extra.dll
- COPYING

## Build environment

- Microsoft Visual Studio 18 Community
- MSVC 14.51.36231
- CMake 4.3.1-msvc1
- Ninja 1.13.2
- Windows SDK 10.0.22621.0 for resource/manifest tooling
- C++20
- x64 RelWithDebInfo

## Build stability

The Windows build initially experienced intermittent compiler/Ninja access violations (0xC0000005). Investigation identified two independent toolchain issues: MSVC debug information generation using /Zi with per-target compile PDB handling, and the Windows SDK 10.0.26100.0 manifest tool (mt.exe) crashing with 0xC0000005.

The successful build used embedded MSVC debug information (/Z7), removed generated TARGET_COMPILE_PDB entries from the working Ninja build, and used the Windows SDK 10.0.22621.0 mt.exe.

## RandomX verification

The resulting bitcoind.exe contains the RandomX section and initialized RandomX proof-of-work verification successfully at runtime.

A fresh test datadir started successfully and reached init message: Done loading.

## Real-chain verification

A copy of the actual PCoin SOLO chain was loaded by the newly built daemon without modifying the live SOLO datadir.

Verified chain height: 11115
Best block: bac0d66ef51b912306cd55b9f180d1ae0057936b77c6bd32c0396dc9d308a63f
Difficulty: 0.1511883284963527
Verification progress: 1
Initial block download: false
Pruned: false
Warnings: none

The daemon verified the last six blocks and reported no coin database inconsistencies.

## RPC verification

The newly built bitcoin-cli.exe successfully queried the newly built bitcoind.exe using RPC port 19543 and returned getblockchaininfo successfully with exit code 0.

## Clean deployment verification

The binaries were copied to a clean deployment directory containing only the required runtime files. The clean bitcoind.exe started successfully with a fresh datadir, initialized RandomX, started networking threads and reached init message: Done loading.

The clean bitcoin-cli.exe reported: PCoin Core RPC client version v29.4.0.

## Release artifact

File: PCoin-Windows-RandomX-Unofficial-2026-10-06.zip
Size: 6,096,570 bytes
SHA-256: E775324AD44559062D6C5BE9AE9F30A73FCAB2374633BCDA0A9BB2B1E1DCA31E

## Contents

| File | Size |
|---|---:|
| bitcoind.exe | 14,778,368 bytes |
| bitcoin-cli.exe | 1,644,544 bytes |
| event_core.dll | 182,272 bytes |
| event_extra.dll | 141,824 bytes |
| COPYING | 1,142 bytes |
| PCoin-RandomX-Windows-Build-Report.md | 3,300 bytes |

## Status and scope

This is an independent community Windows build and is not represented as an official PCoin release. The purpose of publication is to provide an independently tested Windows RandomX binary package for community use and PCoin team review.

## Important safety note

This build is unofficial and has not been verified or endorsed by PCoin. Never enter a recovery phrase for a wallet containing funds into an unofficial wallet binary. Anyone testing unofficial wallet software should use a fresh wallet containing no funds.

The release package contains only the tested runtime binaries, required libevent DLLs, the PCoin MIT license file, and this build report. No private keys, wallet files, personal mining-farm configuration, or private network addresses are included.
