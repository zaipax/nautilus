v0.2.1 修正 Windows 发布结构：将 v0.2.0 携带 Python 运行时的主程序替换为原生 C++ 程序。官方 Pearl Rust 证明库静态链接，已验证的 CUDA 内核原样内嵌。**没有 Python、PYD、附带 DLL、运行时解压或动态下载组件。**

ZIP 1,606,078 字节（约 1.6 MB），EXE 4,021,248 字节（约 4.0 MB）。解压后只有 `nautilus.exe`、`START-MINING.bat`、`README.txt`、`THIRD-PARTY-NOTICES.txt` 和 `FILES-SHA256.txt`。

编辑 BAT 中的钱包和矿工名后双击启动，无需安装 Python、CUDA Toolkit 或额外 VC 运行库。

- 默认矿池：`68.183.184.25:3333`，Reef full-proof 协议。
- 默认钱包：`prl1p3dgtgfxsggfw064la9wt5uqs9vx0mgzm2sdg99lrjemv895vt6ks6p2w3p`。
- 默认 GPU 0、batch 16，支持断线重连、异步证明、过期任务丢弃和 Ctrl+C 停止。
- Windows 10/11 x64、NVIDIA SM120；实测 RTX 5060 Ti 16 GB、驱动 617.14。

当前桌面负载下运行 **600.073 秒**，本地完成搜索量平均 **90.797 TH/s**，矿池接受 **10 份完整证明、0 拒绝**，服务端有效 share ID **308–317**。2 个过期候选/证明在本地丢弃。重新解压到中文和带空格路径后，原样运行 ZIP 中 EXE 又获得有效 share **318**。15 秒本地完整批次基准为 **93.619 TH/s**。

本地算力使用 `pearlhash_hps`，不把提前结束的获胜批次计作完整工作量。这 10 分钟的已接受 share 估算约 **75.051 TH/s**，样本较少、随机波动明显，不能将其与本地完成搜索量直接混用或视作长期矿池平均值。

验证包括独立 CPU 协议/密码学向量、322 组完整 GPU 轨迹、认证失败/不支持任务/异常 JSON/断线重连测试、文件哈希和 BAT 启动。CUDA 搜索内核 SHA256 仍为 `35ce760df86722e9c77a6caf2ababcdecf5b98dc8c5acaf858b72bfa5110cfce`。

EXE 的 PE 导入项仅为 Windows 系统库；CUDA 使用已安装的 NVIDIA 驱动。没有附带源码或 PDB，没有加壳、不修改防护、不添加排除项、不安装服务或开机启动。程序未做 Authenticode 签名。发布流程会在 Windows 运行器上再次自检并完成 Defender 扫描；实际结果见附件 `WINDOWS-VALIDATION.txt`，不能保证其它安全软件或 SmartScreen 不会提醒。

使用附件 `SHA256SUMS.txt` 核对 ZIP；压缩包内提供逐文件校验清单和第三方许可。
