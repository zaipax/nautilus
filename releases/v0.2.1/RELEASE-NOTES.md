Nautilus 0.2.1 replaces the Python-based v0.2.0 host with a native C++ program. The official Pearl Rust proof library is statically linked, and the previously verified CUDA kernels are embedded. There is no Python interpreter, PYD, bundled DLL, self-extracting loader or runtime component download.

The ZIP is 1,606,078 bytes and the EXE is 4,021,248 bytes. It contains nautilus.exe, START-MINING.bat, README.txt, THIRD-PARTY-NOTICES.txt and FILES-SHA256.txt.

Extract the ZIP, edit the wallet and worker name in the BAT, then double-click it. No Python, CUDA Toolkit or extra Visual C++ runtime installation is needed.

- Default pool: 68.183.184.25:3333, Reef full-proof protocol.
- Default wallet: prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p.
- GPU 0 and batch 16 by default, with reconnect, asynchronous proofs, stale-work rejection and Ctrl+C shutdown.
- Windows 10/11 x64, NVIDIA SM120. Verified on RTX 5060 Ti 16 GB, driver 617.14.

Under the existing desktop load, a 600.073-second run averaged **90.797 TH/s of locally completed work**, with **10 accepted full proofs and 0 rejected**. Pool receipts are share IDs 308–317. Two obsolete candidates/proofs were discarded locally. An independently extracted ZIP under a path containing Chinese characters and spaces produced accepted share 318. The 15-second complete-batch local benchmark was **93.619 TH/s**.

The accepted-share estimate for that short window was approximately **75.051 TH/s**. It has considerable statistical variance and is not a claim about sustained pool performance. Local accounting uses pearlhash_hps and does not credit winning batches as complete when they may have stopped early.

Validation covered independent CPU protocol and cryptographic vectors, 322 complete GPU transcripts, authentication failure, unsupported jobs, malformed JSON, reconnect, file checksums and the BAT launcher. The CUDA search image SHA256 is 35ce760df86722e9c77a6caf2ababcdecf5b98dc8c5acaf858b72bfa5110cfce.

The PE import table contains Windows system components; CUDA uses the installed NVIDIA driver. No source or PDB is distributed. The miner does not use a packer, modify security settings, add exclusions, install services or run at startup. It is not Authenticode-signed. The actual Windows runner and Defender results are attached as WINDOWS-VALIDATION.txt; they do not guarantee other antivirus or SmartScreen classifications.

Check the ZIP against SHA256SUMS.txt. Per-file checksums and dependency licenses are included in the archive.
