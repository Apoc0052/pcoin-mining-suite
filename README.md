# PCoin Community Mining Suite

Version: v1.0.7-community.4
Maintainer: Apoc0052

Independent community release of a PCoin-focused XMRig/XMRigCC mining suite.

This is an independent community release and is NOT an official PCoin, XMRig, or XMRigCC release.

## Community Donation

This build includes a fixed 1% community mining-time donation in the modified XMRigCC miner.

Pool: pool.pc.am:3333

Donation address:
pc1qee2yqdm6aak4zk4k2v20a347jyqzlsq28we9pp

The donation connects directly to the public PCoin pool.

It replaces the upstream XMRig/XMRigCC donation destination.

It does not use the user's SOLO server or mining proxy.

The 1% figure refers to mining time, not exactly 1% of PCN earnings.

## Release Contents

The Windows package provides:

- PCoin SOLO mining
- PCoin pool mining
- PCoin DUAL/XMRigCC mode
- XMRigCC-based PCoin rx/pcoin mining
- Thread-control GUI
- Mining monitors
- PCoin SOLO server components
- Ubuntu configuration/support files

Fresh installations require the user to configure their own PCoin wallet address and SOLO server.

## Source

The corresponding modified XMRigCC 3.4.10-dev source is provided as a release asset.

The source includes the PCoin rx/pcoin modifications and the fixed 1% community donation implementation used by the distributed Windows binaries.

## Licensing

XMRigCC is licensed under GPL-3.0. PCoin is licensed under MIT. Other third-party components retain their respective licenses.

See Miner\LICENSES.txt inside the Windows package for detailed third-party licensing information.

## Release Hashes

Windows package:

PCoin-Community-Mining-Suite-v1.0.7-community.4-Windows.zip

SHA-256:
BDA600AFFBAB36689F1BD53F5351C1E37FA437CE605BB8FB5B9DBFC61A0DEFF7

Corresponding source:

PCoin-Community-Mining-Suite-v1.0.7-community.4-source.zip

SHA-256:
55A6FE2B7079B1DBE4836A8B114CBB1BB4869D8C6E16D4C31662233C2400356D

## Release Notes

Changes in v1.0.7-community.4:

- Fixed the miner exiting immediately when the suite folder path contains a space. The daemon now re-quotes the miner command line, so a quoted config path inside a folder such as `Desktop\New folder` is passed through intact instead of being split at the space.
- `xmrigDaemon.exe` now reports a start failure with the Windows error code, for example when antivirus blocks the miner, instead of exiting with no explanation.
- `DONATION-AND-TRUST.txt` names the observed Avira detection, gives per-vendor exclusion steps and states that a vendor may keep the classification.

Carried from v1.0.7-community.3:

- The Miner Terminal shows the live xmrig view on every POOL, SOLO and DUAL start, plus a donation status bar and DPI-aware window sizing.
- The donation scheduler keeps its four-minute window per 6h40m cycle across restarts.
- SOLO startup shows node sync progress and fails with a clear reason on stalls.
- Setup writes one CPU profile for all three modes and validates the pc1 wallet checksum.
- DUAL ships its local controller bound to 127.0.0.1:3344.
- SHA256SUMS.txt, VERIFY-HASHES.bat and BUILDING-MINER.txt are included; all 14 executables can be checked.

Earlier notes:

- Public-release configuration sanitized; no private farm wallet, IPs or machine names.
- Fresh installs require the user to configure their own PCoin wallet and SOLO server.
- Rebuilt XMRigCC 3.4.10-dev PCoin miner with rx/pcoin support.
- Fixed 1% community donation of mining time to the disclosed PCoin donation address.
- Community donation connects directly to pool.pc.am:3333 and replaces the upstream XMRig donation destination.
- XMRigCC server used by DUAL mode is restricted to localhost.
- Updated Windows miner binaries and matching libuv runtime.
- POOL mode tested end-to-end with an accepted PCoin share.

## Disclaimer

Use this software at your own risk. Mining performance, pool availability, network conditions, and PCoin protocol behavior may change.

No private keys, recovery phrases, or personal mining-farm configuration are included in the public release.

PCoin Community Mining Suite v1.0.7-community.4


## Unofficial PCoin Windows RandomX Core Build

A separate unofficial Windows RandomX Core build is available for testing and review:

**Package:** `PCoin-Windows-RandomX-Unofficial-2026-10-06.zip`  
**Based on:** PCoin Core v29.4.0  
**SHA-256:** `E775324AD44559062D6C5BE9AE9F30A73FCAB2374633BCDA0A9BB2B1E1DCA31E`

This is an independent community build. It is **not an official PCoin release and has not been verified or endorsed by PCoin**. The package includes a technical build report documenting the Windows toolchain, RandomX initialization, clean deployment test, RPC test, and real-chain verification performed against a copy of the PCoin SOLO chain.

### Safety

Do not use an unofficial wallet binary with a wallet that contains funds, and never enter a recovery phrase for a funded wallet into unofficial software. Testing should use a fresh wallet with no funds.

The exact package name intentionally avoids official-looking version tags, following PCoin's request that community releases be clearly distinguishable from official releases.
