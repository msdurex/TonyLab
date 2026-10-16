# TonyLab

面向 Windows 的 GPU、CPU 与内存压力测试工具，提供运行监控与 HTML 报告。

## 下载

[下载 TonyLab 0.8.4](https://github.com/msdurex/TonyLab/releases/tag/v0.8.4) · [全部版本](https://github.com/msdurex/TonyLab/releases) · [Dieshot 软件介绍](http://dieshot.com/index.php/tonylab/)

| 架构 | 系统要求 | 发布文件 |
| --- | --- | --- |
| x64 | 原生 Windows 10 2004 x64 或更新版本 | x64 Portable.zip / Setup.msi |
| ARM64 | 原生 Windows 11 ARM64 | ARM64 Portable.zip / Setup.msi |

请从 Releases 的 Assets 下载软件。GitHub 自动生成的 Source code 压缩包不包含应用程序。

## 使用

- 便携版完整解压到可写目录，运行 `TonyLab.exe`；保留内部 `EmberGPU` 目录。
- MSI 按当前用户安装，可自选路径。安装器不会自动开始压力测试，也不会安装传感器驱动。
- 未开始 GPU 测试时三维压力场景关闭；开始后解除测试帧率上限。按 `Esc` 停止，结束后查看 HTML 报告或报告文件夹。
- x64 的 DLSS、DLAA、帧生成与光线重建取决于显卡、驱动和插件；ARM64 版禁用这些功能。

## 监控与验证范围

x64 CPU 封装监控使用 LibreHardwareMonitor / 已安装的 PawnIO。ARM64 使用随包 HWiNFO ARM64，需要传感器和共享内存支持，并遵循其许可限制；普通版共享内存有 12 小时时限。没有有效读数的传感器显示不可用。

0.8.4 已完成发布记录中的主机自动化、包完整性及 x64 部分运行/安装检查。ARM64 已交叉编译并检查原生架构，尚未完成 N1X 实机安装、启动、长时压力负载与 CPU 封装传感器验证。主机检查不能替代目标机实测，短时检查不代表长期稳定性。

## 完整性校验

应用与 MSI 尚未代码签名。请用版本附件 `SHA256SUMS.txt` 核对下载文件。在 PowerShell 运行，例如：

```powershell
Get-FileHash .\TonyLab-0.8.4-Windows-x64-Setup.msi -Algorithm SHA256
```

## 反馈与许可

问题反馈请使用 [Issues](https://github.com/msdurex/TonyLab/issues)，附上软件版本、系统架构、显卡、驱动及复现步骤。

本仓库提供应用发布包和说明，不包含应用源码，未授予开源许可。第三方组件遵循软件包内各自的许可证。
