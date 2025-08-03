# Download Guide

## System Requirements

- macOS 12 or higher.
- Windows 10 or higher.
- Linux with X11 environment.

## macOS

### Manual Download

- Apple Silicon: Download `BongoCat_aarch64.dmg`
- Intel Chip: Download `BongoCat_x64.dmg`

### Homebrew Download

1. Add BongoCat tap source:

```bash
brew tap LongQT-sea/BongoCat-English
```

2. Install:

```bash
brew install --no-quarantine bongo-cat
```

3. Update:

```bash
brew upgrade bongo-cat
```

4. Uninstall:

```bash
brew uninstall --cask bongo-cat

brew untap LongQT-sea/BongoCat-English
```

## Windows

- 64-bit systems: Download `BongoCat_x64.exe`
- 32-bit systems: Download `BongoCat_x86.exe`
- ARM64 architecture: Download `BongoCat_arm64.exe`

## Linux(X11)

### Manual Download

- 64-bit systems:
  - Debian / Ubuntu: Download `BongoCat_amd64.deb`
  - Fedora / RHEL: Download `BongoCat_x86_64.rpm`
  - Universal version: Download `BongoCat_amd64.AppImage`
- ARM64 architecture:
  - Debian / Ubuntu: Download `BongoCat_arm64.deb`
  - Fedora / RHEL: Download `BongoCat_aarch64.rpm`
  - Universal version: Download `BongoCat_aarch64.AppImage`

### AUR Download

- Manjaro / ArchLinux: `yay -S bongo-cat`