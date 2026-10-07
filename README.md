# Nautilus

Windows x64 原生矿工发布仓库。

[下载 v0.2.1 ZIP](https://github.com/zaipax/nautilus/releases/download/v0.2.1/nautilus-0.2.1-windows-x64.zip) · [版本说明与校验文件](https://github.com/zaipax/nautilus/releases/tag/v0.2.1)

v0.2.1 已将 v0.2.0 的 Python 打包主程序替换为 C++ 主程序。官方 Pearl Rust 证明库静态编入 EXE，CUDA 内核内嵌。**没有 Python、PYD、附带 DLL 或自解压加载器**。

ZIP 约 1.6 MB，解压后仅有 5 个文件：

```text
nautilus.exe                 原生程序，约 4.0 MB
START-MINING.bat              双击启动
README.txt                   使用说明
THIRD-PARTY-NOTICES.txt       第三方许可
FILES-SHA256.txt              文件校验清单
```

完整解压，编辑 BAT 中的钱包和矿工名，再双击启动。无需安装 Python、CUDA Toolkit 或额外 VC 运行库。按 Ctrl+C 停止。

- 默认矿池：`68.183.184.25:3333`，Reef full-proof 协议。
- 默认钱包：`prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p`。请核对收款地址。
- 当前仅包含 NVIDIA SM120 内核，实测 RTX 5060 Ti 16 GB，驱动 617.14；不承诺其它显卡或矿池兼容。
- 默认 GPU 0、batch 16，持续挖矿，网络断线自动重连。
- 10 分钟实测：本地完成工作量平均 **90.797 TH/s**；矿池接受 **10 份完整证明，0 拒绝**。
- 本地 TH/s 为 `pearlhash_hps / 10^12`，与矿池短窗口的已接受 share 算力估计不同。

`nautilus.exe --help` 查看参数，`--self-test` 做 CPU 自检，`--validate` 校验 GPU。

不附项目源码和 PDB，不修改 Windows 防护设置，不需要管理员权限。

当前未做 Authenticode 签名；发布流程的 Defender 扫描结果见附件 `WINDOWS-VALIDATION.txt`。单次扫描不能保证其它安全软件或 SmartScreen 的判断。请校验 SHA256，疑似误报应提交厂商复核。
