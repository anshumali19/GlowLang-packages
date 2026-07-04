# GlowLang Package Registry

This repository acts as the public registry for GlowLang packages. 

Contributors can submit their packages via Pull Request to this repository to make them installable via `gdu`.

## Directory Structure
*   `packages/http/`
*   `packages/database/`
*   `packages/ai/`

To submit a package, read our [Contributor Guide](CONTRIBUTING.md).

---

## ⚡ Fast Installation via `gdu` (Glow Dependency Utility)
To install and manage packages, you need `gdu`. You can also use `gdu` to install the entire GlowLang compiler and VM:

### 1. Download `gdu`
Download the pre-compiled `gdu` binary for your platform from the **[GitHub Releases Page](https://github.com/anshumali19/GlowLang-packages/releases)**.

### 2. Run the Installer
Run the following command in your terminal to download, compile, and add the `glowlang` toolchain to your system PATH automatically:

```bash
# On Linux/macOS
gdu install glowlang

# On Windows
gdu.exe install glowlang
```

### 3. Bootstrap from Source (Alternative)
If you do not have a pre-compiled `gdu` binary, you can compile and run `gdu` manually to bootstrap the installation:

```bash
# Clone the packages repository
git clone https://github.com/anshumali19/GlowLang-packages.git
cd GlowLang-packages/gdu

# Install build prerequisites (Debian/Ubuntu)
sudo apt-get install -y libsqlite3-dev libssl-dev

# Compile gdu
#   -lsqlite3 : local package cache/registry
#   -lcrypto  : OpenSSL SHA-256 used for package integrity (gdu verify / Glow.lock)
gcc gdu.c -o gdu -O2 -lsqlite3 -lcrypto
# ...or simply: make

# Install the toolchain
./gdu install glowlang
```
