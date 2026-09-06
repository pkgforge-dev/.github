<p align="center">
    <a href="https://github.com/pkgforge-dev/Anylinux-AppImages">
        <img src="https://github.com/user-attachments/assets/25e88dcc-8e4e-4075-86bc-60e7b5950f9b" width="256">
    </a>
    <br>
    <b><a href="https://github.com/pkgforge-dev">Package Forge Dev</a></b>
</p>

---

## About

[![Discord](https://img.shields.io/discord/1313385177703256064?logo=%235865F2&label=Discord)](https://discord.gg/djJUs48Zbu)
[![Documentation](https://img.shields.io/badge/docs.pkgforge.dev-blue)](https://docs.pkgforge.dev/orgs/pkgforge-dev)

[PkgForge-Dev](https://github.com/pkgforge-dev) is a sub-organization of [PkgForge](https://github.com/pkgforge). It exists to package software that ships no portable build of its own, which in practice means AppImages: several hundred of them, one repository per application, each maintained by whoever cared enough to make it.

They are not tied to us. Download one and it runs, or install it through [soar](https://github.com/pkgforge/soar), which pins these releases like any other upstream.

---

## Start Here

**[Anylinux-AppImages](https://github.com/pkgforge-dev/Anylinux-AppImages)**, [@Samueru-sama](https://github.com/Samueru-sama)'s project, is the index of everything built here and the explanation of why it runs anywhere. Most of what is in this org follows from it.

The short version: these bundle their dependencies rather than borrowing the host's, so they work on musl and glibc alike, and on distributions far older than the machine that built them. The [uruntime](https://github.com/pkgforge-dev/Anylinux-uruntime) mounts with FUSE when it can, falls back to user namespaces when it cannot, and extracts and runs when neither is available. There is nothing to install first, including on NixOS.

- [FAQ](https://github.com/pkgforge-dev/Anylinux-AppImages/blob/main/FAQ.md)
- [How to make these](https://github.com/pkgforge-dev/Anylinux-AppImages/blob/main/HOW-TO-MAKE-THESE.md)
- [Size, against Flatpak](https://github.com/pkgforge-dev/Anylinux-AppImages/blob/main/disk-usage-vs-flatpak.md)

---

## Tooling

The parts the AppImages are built out of, useful on their own:

| Project | Description |
|---------|-------------|
| [Anylinux-sharun](https://github.com/pkgforge-dev/Anylinux-sharun) | Collects an application's libraries next to it and rewires it to use them, which is what makes the result independent of the host. |
| [Anylinux-uruntime](https://github.com/pkgforge-dev/Anylinux-uruntime) | The runtime the images ship, cut down to DwarFS only and widened to more architectures. Forked from [VHSgunzo/uruntime](https://github.com/VHSgunzo/uruntime). |
| [appimagetool](https://github.com/pkgforge-dev/appimagetool) | A Rust implementation, targeting DwarFS and the static runtime rather than the original's assumptions. |
| [AppImageUpdate](https://github.com/pkgforge-dev/AppImageUpdate) | Updates an AppImage over zsync, fetching only the parts that changed. |
| [archlinux-pkgs-debloated](https://github.com/pkgforge-dev/archlinux-pkgs-debloated) | Stripped-down Arch packages, which is most of why these images are smaller than the alternatives. |

---

## Contributing

- **Package something.** If an application ships no portable build, it belongs here. [How to make these](https://github.com/pkgforge-dev/Anylinux-AppImages/blob/main/HOW-TO-MAKE-THESE.md) walks through it, and there are several hundred existing repositories to copy from.
- **Fix one that broke.** Upstream moves, builds rot. Open the issue on the repository it happened in, not here.
- **Improve the tooling.** `sharun` and `appimagetool` are where a fix helps every image at once.

---

## AI Policy

AI-assisted contributions are welcome. We do not ask what wrote your patch, and the answer is not held against you. What matters is whether it is correct, whether you understand it, and whether you ran it. That is the same standard a hand-written patch meets.

It does rule out four things:

- **Read what you send.** A pull request you have not reviewed, cannot explain, and did not test is not a contribution. Volume does not substitute for any of the three.
- **Do not open issues you have not reproduced.** A generated bug report costs more time than a bad patch, because the behaviour it describes may never have happened.
- **Do not send generated security reports.** A plausible vulnerability that does not exist takes attention away from one that does. Report what you have confirmed.
- **A build recipe you have not run is a guess.** Invented URLs, versions and dependency lists all look plausible and none of them build. Run it, launch the result, and say which distribution you launched it on.

None of this is specific to AI, and we would ask it of anyone. AI is just what made it cheap to produce work that skipped all four, which is the only reason it needs saying.

---

## Community

<a href="https://discord.gg/djJUs48Zbu">
    <img src="https://github.com/user-attachments/assets/5a336d72-6342-4ca5-87a4-aa8a35277e2f" width="18" height="18">
    <strong>PkgForge Discord</strong>
</a> `➼` <code>https://discord.gg/djJUs48Zbu</code>
