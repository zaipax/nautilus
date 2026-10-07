# Nautilus

Native Windows x64 Pearl miner.

[Download v0.2.2 ZIP](https://github.com/zaipax/nautilus/releases/download/v0.2.2/nautilus-0.2.2-windows-x64.zip) · [Release notes and checksums](https://github.com/zaipax/nautilus/releases/tag/v0.2.2)

Version 0.2.2 prepares new pool jobs in the background to reduce GPU idle time during job changes. The release notes include measured results and remaining limitations.

The host program is C++20. The official Pearl Rust proof library is statically linked, and the verified CUDA kernels are embedded in the EXE. No Python interpreter, PYD, bundled DLLs or self-extracting loader are included.

The ZIP contains exactly five files:

- nautilus.exe — native executable.
- START-MINING.bat — double-click launcher.
- README.txt — usage instructions.
- THIRD-PARTY-NOTICES.txt — dependency licenses.
- FILES-SHA256.txt — per-file checksums.

Extract the entire ZIP, edit the wallet and worker name in START-MINING.bat, then double-click it. Press Ctrl+C to stop. Python, CUDA Toolkit, extra Visual C++ runtime packages and administrator privileges are not required.

- Default pool: 68.183.184.25:3333, using the Reef full-proof protocol.
- Default wallet: prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p. Check your payout address before mining.
- Platform: Windows 10/11 x64 and NVIDIA SM120. Verified on RTX 5060 Ti 16 GB, driver 617.14. Other GPU architectures and pool protocols are not supported by this build.
- Defaults: GPU 0, batch 16, continuous mining with automatic reconnect.
- Local TH/s means pearlhash_hps / 10^12. A pool estimate based on accepted shares uses a different measurement method and fluctuates over short intervals.

Run nautilus.exe --help for options, --self-test for CPU checks, or --validate for GPU correctness checks.

The miner does not modify Windows protection settings, install services or change GPU clocks. It is currently unsigned. See WINDOWS-VALIDATION.txt attached to the release for the actual Defender scan result; a scan cannot guarantee future antivirus or SmartScreen classifications.
