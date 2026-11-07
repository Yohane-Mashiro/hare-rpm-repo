# Hare RPM Repository

This is a Fedora-compatible RPM repository containing the latest x86_64 and ARM64/aarch64 RPM packages from:

- [CC-Switch](https://github.com/farion1231/cc-switch/releases)
- [X Minecraft Launcher](https://github.com/Voxelum/x-minecraft-launcher/releases)
- [YAQMC](https://github.com/YAQMC/YAQMC/releases)
- [Rayburst](https://github.com/AnInsomniacy/rayburst/releases)
- [Clash Verge Rev](https://github.com/clash-verge-rev/clash-verge-rev/releases)
- [FlClash](https://github.com/chen08209/FlClash/releases)
- [iloader](https://github.com/nab138/iloader/releases)

GitHub Actions runs daily and can also be started manually. It temporarily downloads RPMs to generate repository metadata, then removes them and rewrites the metadata to use each project's official GitHub Release URLs. The `gh-pages` branch therefore stores only small metadata files, not RPM packages.

## Usage

Install the repository configuration:

```bash
sudo curl --fail --location --output /etc/yum.repos.d/hare-rpm-repo.repo https://raw.githubusercontent.com/Yohane-Mashiro/hare-rpm-repo/gh-pages/hare-rpm-repo.repo
sudo dnf clean all
sudo dnf makecache
```

Then install packages normally. RPM files are downloaded directly from the upstream projects over HTTPS.

For the Chinese documentation, see [README.md](README.md).

> WPS Linux is not included yet because the official page currently does not expose a verifiable stable RPM download URL.
