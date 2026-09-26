# gitnado-bin

[![AUR version](https://img.shields.io/aur/version/gitnado-bin)](https://aur.archlinux.org/packages/gitnado-bin)

An [AUR](https://aur.archlinux.org/) package for **Gitnado** — a fast,
privacy-first Git GUI client built with Tauri, Lit and Rust.

- Upstream: <https://github.com/hegsie/gitnado>
- Website: <https://gitnado.dev>
- This package repackages upstream's prebuilt `x86_64` `.deb` release.

## Install

With an AUR helper:

```sh
yay -S gitnado-bin
# or
paru -S gitnado-bin
```

Manually:

```sh
git clone https://aur.archlinux.org/gitnado-bin.git
cd gitnado-bin
makepkg -si
```

## Notes

- `x86_64` only — upstream does not publish a Linux ARM build.
- Gitnado was formerly **Leviathan**. This package provides and conflicts with
  `leviathan`, so it cleanly replaces `leviathan-bin`.
- The application delegates advanced operations (rebase, submodules, LFS, GPG
  signing, …) to the system `git`, which is a hard dependency.

## Updating

1. Bump `pkgver` in `PKGBUILD` (and reset `pkgrel=1` if needed).
2. Refresh checksums: `updpkgsums`.
3. Regenerate metadata: `makepkg --printsrcinfo > .SRCINFO`.
4. Build and sanity-check: `makepkg -f && namcap PKGBUILD gitnado-bin-*.pkg.tar.zst`.

## Disclaimer

This package is community-maintained and is not an official Gitnado release
channel. Report packaging issues here; report application bugs upstream.

## License

MIT — see upstream's [LICENSE](https://github.com/hegsie/gitnado/blob/main/LICENSE).
