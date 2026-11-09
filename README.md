# Hare RPM 软件源

这是一个 Fedora 兼容 RPM 软件源，包含以下项目最新 x86_64 和 ARM64/aarch64 RPM 包：

- [CC-Switch](https://github.com/farion1231/cc-switch/releases)
- [X Minecraft Launcher](https://github.com/Voxelum/x-minecraft-launcher/releases)
- [YAQMC](https://github.com/YAQMC/YAQMC/releases)
- [Rayburst](https://github.com/AnInsomniacy/rayburst/releases)
- [Clash Verge Rev](https://github.com/clash-verge-rev/clash-verge-rev/releases)
- [FlClash](https://github.com/chen08209/FlClash/releases)
- [iloader](https://github.com/nab138/iloader/releases)
- [Tyranor Next Linux](https://github.com/Yohane-Mashiro/Tyranor-Next-linux/releases)

GitHub Actions 每天自动运行，也可以手动触发。工作流会临时下载 RPM 生成软件源元数据，然后删除 RPM 文件，并把元数据中的下载地址改为各项目的官方 GitHub Release 链接。因此 `gh-pages` 只保存少量元数据，不保存 RPM 文件。

## 使用方式

安装软件源配置：

```bash
sudo curl --fail --location --output /etc/yum.repos.d/hare-rpm-repo.repo https://raw.githubusercontent.com/Yohane-Mashiro/hare-rpm-repo/gh-pages/hare-rpm-repo.repo
sudo dnf clean all
sudo dnf makecache
```

然后使用正常的软件包名安装。RPM 文件会直接从上游项目的官方 HTTPS 链接下载。

英文版文档请参阅 [README-en.md](README-en.md)。

> WPS Linux 暂未加入：官方页面当前未能提供可验证的稳定 RPM 下载地址。
