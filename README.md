# PCoin Community Mining Suite

Version: v1.0.6-community.3
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

PCoin-Community-Mining-Suite-v1.0.6-community.3-Windows.zip

SHA-256:
FEBDAF32E8FDB1041E82524775824D657A62B21C8E94062CD2BFE2AF3E47D16D

Corresponding XMRigCC source:

PCoin-XMRigCC-Source-v1.0.6-community.3.zip

SHA-256:
85A62DBA0F0FC1D398A70EB17145D9088F32312061562C0CB5EBA7F8933CB6C6

## Release Notes

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

PCoin Community Mining Suite v1.0.6-community.3


## Unofficial PCoin Windows RandomX Core Build

A separate unofficial Windows RandomX Core build is available for testing and review:

**Package:** `PCoin-Windows-RandomX-Unofficial-2026-10-06.zip`  
**Based on:** PCoin Core v29.4.0  
**SHA-256:** `E775324AD44559062D6C5BE9AE9F30A73FCAB2374633BCDA0A9BB2B1E1DCA31E`

This is an independent community build. It is **not an official PCoin release and has not been verified or endorsed by PCoin**. The package includes a technical build report documenting the Windows toolchain, RandomX initialization, clean deployment test, RPC test, and real-chain verification performed against a copy of the PCoin SOLO chain.

### Safety

Do not use an unofficial wallet binary with a wallet that contains funds, and never enter a recovery phrase for a funded wallet into unofficial software. Testing should use a fresh wallet with no funds.

The exact package name intentionally avoids official-looking version tags, following PCoin's request that community releases be clearly distinguishable from official releases.

