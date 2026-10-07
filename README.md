# Nautilus

Windows x64 矿工二进制发布仓库。

[下载 v0.2.0 ZIP](https://github.com/zaipax/nautilus/releases/download/v0.2.0/nautilus-0.2.0-windows-x64.zip) · [版本说明与校验文件](https://github.com/zaipax/nautilus/releases/tag/v0.2.0)

完整解压 ZIP，编辑 `START-MINING.bat` 中的钱包和矿工名，然后双击启动。无需安装 Python 或 CUDA Toolkit。按 Ctrl+C 停止。

- 默认矿池：`68.183.184.25:3333`，Reef full-proof 协议。
- 默认钱包：`prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p`。请核对收款地址。
- 当前仅包含 NVIDIA SM120 内核，实测 RTX 5060 Ti 16 GB，驱动 617.14；不承诺其它显卡或矿池兼容。
- 默认 batch 16，持续挖矿，网络断线自动重连；日志保留最近 24 个会话。
- 本地 TH/s 为 `pearlhash_hps / 10^12`，与矿池短窗口的已接受 share 算力估计不同。

程序采用原生编译保护，CUDA 内核以 cubin 提供，不附项目源码和 PDB。使用普通展开目录，不加自解压壳，不修改 Windows 防护设置，不需要管理员权限。

本版本未做 Authenticode 签名，无法保证没有 SmartScreen 信誉提醒或杀软误报。构建机未提供有效的 Defender 扫描；发布流程的检查结果见 Release 附件 `WINDOWS-VALIDATION.txt`。请校验 SHA256 并扫描下载包，遇到疑似误报应提交厂商复核，不要关闭防护。
