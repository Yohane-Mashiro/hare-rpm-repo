# RPM repositories

This repository publishes the latest Linux RPM packages from these upstream projects as Fedora-compatible DNF/YUM repositories:

- [CC-Switch](https://github.com/farion1231/cc-switch/releases)
- [X Minecraft Launcher](https://github.com/Voxelum/x-minecraft-launcher/releases)
- [YAQMC](https://github.com/YAQMC/YAQMC/releases)
- [Rayburst](https://github.com/AnInsomniacy/rayburst/releases)

The GitHub Actions workflow runs daily and can also be started manually. It downloads the latest x86_64 and ARM64/aarch64 RPM assets, regenerates each `repodata/` directory with `createrepo_c`, and force-updates the `gh-pages` branch.

Install any repository with:

```bash
sudo curl --fail --location \\
  --output /etc/yum.repos.d/cc-switch.repo \\
  https://raw.githubusercontent.com/Yohane-Mashiro/hare-rpm-repo/gh-pages/cc-switch/cc-switch.repo
sudo dnf install cc-switch
```

Replace `cc-switch` in both the filename and URL with `xmcl`, `yaqmc`, or `rayburst` for the other repositories. Each repository is regenerated from scratch, so obsolete versions are not retained.

These repositories currently do not provide GPG-signed repository metadata, so `gpgcheck=0` is used in the generated `.repo` files. Upstream release assets are downloaded over HTTPS from GitHub.
