# Next QR Code Generator

A addon to generate Chromium-style QR codes featuring the iconic Firefox logo.

## 🌟 Features

- **Chromium-Style QR Codes**: Generates QR codes with the exact same styling as Chrome's native implementation
- **Firefox Logo Center**: Features the Firefox logo in the center of QR codes
- **Instant Generation**: Automatically generates QR codes for the current page URL
- **Custom Text Support**: Create QR codes for any text or URL you enter
- **One-Click Copy**: Copy QR codes to clipboard as high-quality PNG images
- **Easy Download**: Download QR codes with smart filename generation
- **Perfect Sizing**: Matches Chrome's exact QR code dimensions and styling
- **Dark Mode Support**: Seamlessly integrates with your browser's theme

## 🚀 Installation

### From Firefox Add-ons Store

You can install the extension directly from the [Firefox Add-ons Store](https://addons.mozilla.org/en-US/firefox/addon/next-qrcode-generator/).

### Manual Installation (Development)

1. **Clone the repository**

   ```bash
   git clone https://github.com/chromium-style-qrcode/next-qrcode-generator.git
   cd next-qrcode-generator
   ```

2. **Install dependencies**

   ```bash
   pnpm install
   ```

3. **Build the extension**

   ```bash
   pnpm build
   ```

4. **Load in Firefox**
   - Open Firefox and navigate to `about:debugging#/runtime/this-firefox`
   - Click "Load Temporary Add-on"
   - Select the `manifest.json` file from the `.output/firefox-mv2` folder

## 🎯 Usage

1. **Access the Extension**: Click the QR code icon in your browser's toolbar
2. **Shortcut Access**: Use the shortcut `Alt+Shift+Q` (Windows/Linux) or `⌥⇧Q` (Mac) to quickly open the extension
3. **Auto-Fill Current URL**: The extension automatically loads the current page's URL
4. **Custom Text**: Replace the URL with any text you want to convert to a QR code
5. **Copy to Clipboard**: Click the "Copy" button to copy the QR code as an image
6. **Download**: Click "Download" to save the QR code as a PNG file

> **Note**: If the shortcut does not work in Firefox, go to `about:addons` → Click the gear icon in the top right → "Manage Extension Shortcuts" to check or reconfigure the shortcut.

## 🛠️ Technology Stack

- **Framework**: [WXT](https://wxt.dev/) - Modern web extension framework
- **Frontend**: React 19 + TypeScript
- **Styling**: Tailwind CSS 4.0 + Radix UI components
- **QR Generation**: WebAssembly (WASM) module for Chromium-exact QR code generation
- **Build System**: Vite + Rollup
- **Package Manager**: pnpm

## 🔧 Development

### Prerequisites

- Node.js ≥ 22.18.0
- pnpm ≥ 11.0.9

### Development Commands

```bash
# Start development server
pnpm dev

# Build for production
pnpm build

# Create distribution zip
pnpm zip

# Type checking
pnpm compile

# Format code
pnpm format

# Generate/update CHANGELOG.md from Conventional Commits (latest changes)
pnpm changelog

# Initialize (regenerate for all history)
pnpm changelog:init
```

### Project Structure

```tree
src/
├── components/
│   └── ui/           # Reusable UI components
├── hooks/
│   ├── use-qrcode.ts # QR code generation logic
│   └── use-dark-mode.ts
├── lib/
│   ├── wasm-loader.ts    # WASM module loader
│   └── utils.ts
├── popup/
│   ├── App.tsx       # Main popup component
│   └── main.tsx      # Entry point
├── providers/
│   └── theme.tsx     # Theme provider
├── styles/
│   └── base.css      # Global styles
└── types/            # TypeScript type definitions
```

## 🎨 Features in Detail

### Chromium-Exact QR Generation

The extension uses a WebAssembly module that replicates Chrome's native QR code generation algorithm, ensuring:

- Identical visual appearance to Chrome's built-in QR codes
- Same module styling (circles vs squares)
- Rounded locator patterns
- Exact sizing and margins

### Smart Filename Generation

Downloaded QR codes automatically get meaningful filenames:

- `qrcode_example.com.png` for domain names
- `qrcode_firefox.png` for other content

### Accessibility

- Full keyboard navigation support
- Screen reader compatible
- High contrast mode support
- Proper ARIA labels and descriptions

## 🚀 Releases

This project uses automated releases through GitHub Actions.

### Creating a Release

```bash
# Stable release (publish to store)
pnpm version 1.0.0
git push origin main
git push origin 1.0.0

# Pre-release (GitHub only)
pnpm version prerelease --preid='[alpha｜beta|rc]'
git push origin main
git push origin 1.0.0-alpha.0
```

### Version Types

- **Stable** (1.0.0): Auto-published to Firefox Add-ons Store
- **Alpha/Beta/RC** (1.0.0-alpha.0): GitHub releases only for testing

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Development Guidelines

1. Follow the existing code style
2. Add TypeScript types for new features
3. Test on Firefox
4. Update documentation as needed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Chrome team for the original QR code implementation
- [WXT](https://wxt.dev/) for the excellent extension framework
- [Radix UI](https://www.radix-ui.com/) for accessible components
- [Tailwind CSS](https://tailwindcss.com/) for styling utilities

## 📞 Support

If you encounter any issues or have questions:

- Open an issue on [GitHub](https://github.com/chromium-style-qrcode/next-qrcode-generator/issues)
