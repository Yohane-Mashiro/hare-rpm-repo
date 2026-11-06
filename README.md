# Hare RPM 软件源

这是一个**单一的 Fedora 兼容 RPM 软件源**，包含以下项目的最新 x86_64 和 ARM64/aarch64 RPM 包：

- [CC-Switch](https://github.com/farion1231/cc-switch/releases)
- [X Minecraft Launcher](https://github.com/Voxelum/x-minecraft-launcher/releases)
- [YAQMC](https://github.com/YAQMC/YAQMC/releases)
- [Rayburst](https://github.com/AnInsomniacy/rayburst/releases)

GitHub Actions 每天自动运行，也可以手动触发。工作流会将所有上游 RPM 下载到同一个目录，使用 `createrepo_c` 生成一个统一的 `repodata/`，然后强制更新 `gh-pages` 分支。

## 使用方式

安装这个单一软件源：

```bash
sudo curl --fail --location \\
  --output /etc/yum.repos.d/hare-rpm-repo.repo \\
  https://raw.githubusercontent.com/Yohane-Mashiro/hare-rpm-repo/gh-pages/hare-rpm-repo.repo
sudo dnf makecache
```

然后使用正常的软件包名安装：

```bash
sudo dnf install cc-switch
sudo dnf install xmcl
sudo dnf install yaqmc
sudo dnf install rayburst
```

每次同步都会从头生成软件源，因此不会保留已经废弃的旧版本。目前本软件源没有提供 GPG 签名的软件源元数据，因此生成的配置使用 `gpgcheck=0`。上游 RPM 包通过 HTTPS 从 GitHub 下载。

英文版文档请参阅 [README-en.md](README-en.md)。
