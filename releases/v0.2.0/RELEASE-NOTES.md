Nautilus 0.2.0 Windows x64 发布版。完整解压 ZIP 后，编辑并双击 `START-MINING.bat` 即可挖矿，无需安装 Python 或 CUDA Toolkit。

- 默认矿池：`68.183.184.25:3333`，Reef full-proof 协议。
- 默认钱包：`prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p`。
- 保留最佳 TMA 内核，默认 batch 16；断线重连、Ctrl+C 停止、日志按会话保留。
- 主程序采用原生编译保护，CUDA 内核发布 cubin，不附项目源码或 PDB。

**硬件范围：** Windows 10/11 x64，NVIDIA SM120；实测 RTX 5060 Ti 16 GB、驱动 617.14。使用 GPU 0，仅验证 Reef full-proof 矿池协议。

**实测：** 当前桌面负载下运行 600.125 秒，本地完成搜索量平均 **91.215 TH/s**；矿池接受 **6 份有效证明，0 拒绝**，服务端回查有效 share ID 301–306。另有 2 个候选因任务过时在本地丢弃。48 项测试通过，解压包的文件哈希、BAT 和独立运行入口通过检查。

本地 TH/s 采用 `pearlhash_hps` 口径。该 10 分钟窗口的 6 份 share 换算为约 45.03 TH/s 的已接受工作量估计，样本很少、波动很大；这两个统计口径不能混用，本次结果不代表长期矿池平均算力。

**Windows 安全：** 普通展开目录，无 UPX 或自解压壳，不修改系统防护、不添加排除项、不安装服务或开机启动。本版本未做 Authenticode 签名，不能保证没有 SmartScreen 提醒或安全软件误报。构建机无法提供有效 Defender 扫描；发布流程的实际 Windows 检查结果见附件 `WINDOWS-VALIDATION.txt`。不要关闭防护来运行，疑似误报应向安全厂商申请复核。

下载后可用 `Get-FileHash .\nautilus-0.2.0-windows-x64.zip -Algorithm SHA256` 与附件 `SHA256SUMS.txt` 比较。压缩包内同时提供每个文件的校验清单、中文说明和第三方许可。
