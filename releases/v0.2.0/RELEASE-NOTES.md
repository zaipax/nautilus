Nautilus 0.2.0 for Windows x64. This historical release packages the Python-based validation host with its runtime dependencies. It has been superseded by the native C++ releases.

Extract the complete ZIP, edit START-MINING.bat and double-click it. A separate Python or CUDA Toolkit installation is not required.

- Default pool: 68.183.184.25:3333, Reef full-proof protocol.
- Default wallet: prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p.
- Retained TMA kernel, batch 16, automatic reconnect, Ctrl+C shutdown and bounded session logs.
- Windows 10/11 x64, NVIDIA SM120. Verified on RTX 5060 Ti 16 GB, driver 617.14, GPU 0.

A 600.125-second run under the existing desktop load averaged **91.215 TH/s of locally completed work**, with **6 accepted full proofs and 0 rejected**. Pool receipts are share IDs 301–306. Two obsolete candidates/proofs were discarded locally. The release passed 48 tests, file checksums, launcher checks and extraction tests.

The six-share estimate was approximately **45.03 TH/s** for this short window, with substantial statistical variance. It is a different measurement from local completed-work rate and is not evidence of sustained pool performance.

The package uses an ordinary extracted directory, without UPX or a self-extracting loader. It does not modify system protection, add exclusions, install a service or configure startup. It is unsigned. The actual Windows and Defender validation results are attached as WINDOWS-VALIDATION.txt; they do not guarantee future antivirus or SmartScreen classifications.

Verify the ZIP using SHA256SUMS.txt. The archive includes per-file checksums and third-party licenses.
