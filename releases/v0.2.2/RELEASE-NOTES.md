Nautilus 0.2.2 reduces GPU idle time when a new pool job arrives. Receiving and CPU commitment preparation now run in the background while the current GPU batch executes. Clean-job invalidation is delivered before preparation finishes, and the search waits for prepared seeds before using the next job. The retained CUDA search kernel and proof protocol are unchanged.

The CLI, launcher prompts, packaged README, repository README and release notes are in English. The descriptions for v0.2.0 and v0.2.1 have also been translated; their historical ZIP files are unchanged.

The Windows ZIP is 1,616,094 bytes and contains exactly five files: nautilus.exe, START-MINING.bat, README.txt, THIRD-PARTY-NOTICES.txt and FILES-SHA256.txt. The EXE is 4,050,944 bytes. The host is native C++20, the official Pearl Rust prover is statically linked, and CUDA kernels are embedded. No Python interpreter, PYD or runtime DLL is bundled.

Extract the entire ZIP, edit the wallet and worker in START-MINING.bat, then double-click it. Press Ctrl+C to stop. No Python, CUDA Toolkit, extra Visual C++ runtime installation or administrator privileges are required.

- Default pool: 68.183.184.25:3333, using the Reef full-proof protocol.
- Default wallet: prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p. Check your payout address before mining.
- Windows 10/11 x64, NVIDIA SM120. Verified on RTX 5060 Ti 16 GB, driver 617.14.
- GPU 0, batch 16, continuous mining, automatic reconnect and asynchronous CPU proofs.

Validation under the existing desktop and screen-streaming workload:

- A 300.023-second real-pool run averaged **91.568 TH/s of locally completed work**, with **4 accepted full proofs and 0 rejected**. Pool receipts are share IDs 330-333. Sampled GPU utilization after the first 10 seconds averaged **99.19%**; brief dips remain, including an 81% minimum during CPU proof generation. Proof completion to submission took 1-2 ms in this run.
- A separate 20-second loopback stress replay issued a new clean job every second. Utilization samples after the first 10 seconds averaged **82.33% before / 99.24% after**, with minima of 30% / 99%. This artificial workload isolates scheduling overhead; it is not a real-pool hashrate gain.
- CPU fixtures and asynchronous handoff/error tests, **322 complete GPU transcripts**, and socket cases for authorization rejection, unsupported jobs, deeply nested JSON and reconnect all passed.
- The final ZIP was extracted under a path containing Chinese characters and spaces. Its BAT launcher, English prompts, Windows version metadata and all file hashes passed; the extracted miner submitted accepted share **334** with no rejection.

Local TH/s uses pearlhash_hps / 10^12 with work factor 1,048,576, equivalent to 87.326 million completed tile attempts/s in the real-pool run. Winning batches are not counted as complete. The four accepted shares imply approximately 60.04 TH/s over this short window; that statistical estimate uses a different method and is not evidence of sustained pool performance. Desktop activity, CPU proofs and late-arriving jobs can still cause brief utilization dips. The miner does not change GPU clocks or close desktop applications.

CUDA search image SHA256: 35ce760df86722e9c77a6caf2ababcdecf5b98dc8c5acaf858b72bfa5110cfce.

Verify the ZIP with SHA256SUMS.txt and individual files with FILES-SHA256.txt. The release workflow checks the archive, runs CPU self-tests on a clean Windows runner and scans the extracted package with Defender before publication. The actual results are attached as WINDOWS-VALIDATION.txt. The miner is unsigned and does not modify Windows protection settings, add exclusions, install services, run at startup or use a packer. A scan does not guarantee future antivirus or SmartScreen classifications.
