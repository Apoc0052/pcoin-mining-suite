# PCoin Community Mining Suite

Version: v1.0.6-community.1
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

PCoin-Community-Mining-Suite-v1.0.6-community.1-Windows.zip

SHA256:
31DE5E2709130B1E1B00742090A608A13208AC773207F44A84214DC398DC2FCC

Corresponding XMRigCC source:

PCoin-XMRigCC-Source-v1.0.6-community.1.zip

SHA256:
0809C7A967D7346BA76B5E107EC189A8CBDFE91290BDBEE08E60BDFF73119802

## Disclaimer

Use this software at your own risk. Mining performance, pool availability, network conditions, and PCoin protocol behavior may change.

No private keys, recovery phrases, or personal mining-farm configuration are included in the public release.

PCoin Community Mining Suite v1.0.6-community.1