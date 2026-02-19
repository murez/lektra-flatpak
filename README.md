# Lektra Flatpak

Flatpak packaging for [Lektra](https://github.com/dheerajshenoy/lektra) - a high-performance PDF reader that prioritizes screen space and control.

## Building

### Prerequisites

- Flatpak
- Flatpak Builder

Install them with:
```bash
# On Fedora
sudo dnf install flatpak flatpak-builder

# On Ubuntu/Debian
sudo apt install flatpak flatpak-builder

# On Arch Linux
sudo pacman -S flatpak flatpak-builder
```

### Build Steps

1. Clone this repository:
```bash
git clone https://github.com/dheerajshenoy/lektra-flatpak.git
cd lektra-flatpak
```

2. Add the Flathub remote (if not already added):
```bash
flatpak remote-add --user --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

3. Install the runtime and SDK:
```bash
flatpak install --user flathub org.kde.Platform/x86_64/6.6 org.kde.Sdk/x86_64/6.6
```

4. Build the application:
```bash
flatpak-builder --user --install --force-clean build-dir io.github.dheerajshenoy.lektra.yml
```

5. Run the application:
```bash
flatpak run io.github.dheerajshenoy.lektra
```

## Features

- High-performance PDF rendering using MuPDF
- Minimal UI with maximum screen space for content
- Advanced features like:
  - Tabs and splits
  - Portals
  - Multiple layouts
  - Outline overlay
  - Search with scrollbar highlights
  - Jump markers
  - Link hints
  - Command palette
  - SyncTeX integration

## Notes

- **LLM support is disabled** in this Flatpak build for security and size considerations
- The application requires access to the home directory to open PDF files (can be customized)
- This is an alpha version - bugs and crashes are expected

## License

This Flatpak packaging is provided under the same license as Lektra (AGPL-3.0)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) in the Lektra repository.