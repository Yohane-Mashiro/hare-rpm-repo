# CC-Switch RPM repository

This repository publishes the latest x86_64 and arm64 RPM packages from [farion1231/cc-switch](https://github.com/farion1231/cc-switch/releases) as a Fedora-compatible DNF/YUM repository.

The GitHub Actions workflow runs daily and can also be started manually. It downloads the latest upstream release, regenerates `repodata/` with `createrepo_c`, and force-updates the `gh-pages` branch with the repository contents.

Install the repository with:

```bash
sudo curl --fail --location \\
  --output /etc/yum.repos.d/cc-switch.repo \\
  https://raw.githubusercontent.com/Yohane-Mashiro/hare-rpm-repo/gh-pages/cc-switch.repo
sudo dnf install cc-switch
```

The upstream RPM package metadata currently uses the package name `cc-switch`. Repository metadata is regenerated from scratch on each run, so obsolete versions are not retained.

This repository currently does not provide a GPG-signed repository, so `gpgcheck=0` is used in the generated repo file. The upstream release assets are downloaded over HTTPS from GitHub.
