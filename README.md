# WINProductKey

This application is a simple tool built with Rust and Tauri to retrieve the Windows product key from the system registry. It uses Tauri to provide a minimal web-based interface and Rust for accessing and processing the registry data.

## Features

- Retrieve the Windows product key from the registry.
- UI using Tauri's WebView.
- Lightweight and fast.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- **Rust**: You need to have Rust installed on your machine. You can install Rust using [rustup](https://rustup.rs/).
- **Bun**: Tauri requires Bun or Node.js for building the frontend part. You can install Bun from [here](https://bun.sh/).
- **Tauri CLI**: Install the Tauri CLI by running:
  ```bash
  bun add -D @tauri-apps/cli
  ```

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/VdanielVPL/WINProductKey.git
cd WINProductKey
```

### 2. Install dependencies

```bash
# Install frontend dependencies using Bun
bun install
```

### 3. Build the application

```bash
# Build the Tauri app optimized for release
bunx tauri build
```
```bash
# or run app for development
bunx tauri dev
```

### 4. Run the application (if release version)

in `./src-tauri/target/release` double click on `.exe` file

## Downloading the Executable

If you do not wish to build the application yourself, you can download the pre-built executable directly from the [Releases](https://github.com/VdanielVPL/WINProductKey/releases) section of the GitHub repository.

1. Navigate to the [Releases](https://github.com/VdanielVPL/WINProductKey/releases) page.
2. Download the latest version of the executable (`.exe`) file.
3. Run the downloaded executable to retrieve your Windows product key.

## Usage

When you run the application, it will display a simple UI that shows you your product key.

## How It Works

This program reads the Windows product key from the registry by accessing the following registry path:

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\DigitalProductId
```

The key is stored in a binary format, which the Rust backend decodes into a readable product key.

### Key Files

- **`src-tauri/src/main.rs`**: The Rust backend, which handles registry access and product key decoding.
- **`src/main.ts`**: Simple script calling Rust for product key.
- **`src-tauri/tauri.conf.json`**: Tauri configuration file.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request with your improvements (I'll check them out when I have time).

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Tauri](https://tauri.app/) for making cross-platform desktop applications easy with Rust and WebView.
- [Rust](https://www.rust-lang.org/) for providing a robust and safe systems programming language.
