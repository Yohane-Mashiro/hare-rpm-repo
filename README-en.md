# Hare RPM Repository

This is **one Fedora-compatible RPM repository** containing the latest x86_64 and ARM64/aarch64 RPM packages from:

- [CC-Switch](https://github.com/farion1231/cc-switch/releases)
- [X Minecraft Launcher](https://github.com/Voxelum/x-minecraft-launcher/releases)
- [YAQMC](https://github.com/YAQMC/YAQMC/releases)
- [Rayburst](https://github.com/AnInsomniacy/rayburst/releases)
- [Clash Verge Rev](https://github.com/clash-verge-rev/clash-verge-rev/releases)
- [FlClash](https://github.com/chen08209/FlClash/releases)
- [iloader](https://github.com/nab138/iloader/releases)

GitHub Actions runs daily and can also be started manually. The workflow downloads all upstream RPMs into one directory, generates one `repodata/` directory with `createrepo_c`, and force-updates the `gh-pages` branch.

## Usage

Install this single repository:

```bash
sudo curl --fail --location --output /etc/yum.repos.d/hare-rpm-repo.repo https://raw.githubusercontent.com/Yohane-Mashiro/hare-rpm-repo/gh-pages/hare-rpm-repo.repo
sudo dnf makecache
```

Then install packages by their normal package names:

```bash
sudo dnf install cc-switch
sudo dnf install xmcl
sudo dnf install YAQMC
sudo dnf install rayburst
sudo dnf install clash-verge
sudo dnf install flclash
sudo dnf install iloader
```

The repository is regenerated from scratch on each run, so obsolete versions are not retained. It currently does not provide GPG-signed repository metadata, so `gpgcheck=0` is used. Upstream RPM assets are downloaded over HTTPS from GitHub.

For the Chinese documentation, see [README.md](README.md).

> WPS Linux is not included yet because the official page currently does not expose a verifiable stable RPM download URL.
