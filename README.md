# Overseer terminal

A standalone AI assistant for your terminal. Use installed Ollama models or configure a cloud provider in Settings. Models and optional speech tools are separate installations.

This repository contains public downloads and installation instructions. Product source is maintained separately in a private repository.

## Install with Homebrew

Supported for this preview: Apple Silicon Mac and Ubuntu 24.04-compatible Linux x64.

```sh
brew install Jeccoman/tap/overseer
overseer-tui
```

On Linux, install your system's ALSA runtime (`libasound2t64` on Ubuntu 24.04) if it is missing. Other Linux distributions and older Mac versions have not been accepted here.

## Download an archive

[Open the terminal preview release](https://github.com/Jeccoman/overseer-downloads/releases/tag/terminal-v0.1.4-preview.1).

| Platform | Archive |
| --- | --- |
| Apple Silicon Mac | `overseer-terminal-v0.1.4-aarch64-apple-darwin.tar.gz` |
| Linux x64 | `overseer-terminal-v0.1.4-x86_64-unknown-linux-gnu.tar.gz` |
| Windows x64 | `overseer-terminal-v0.1.4-x86_64-pc-windows-msvc.zip` |

Download the matching archive and its `.sha256` file. In the download folder, verify it with `shasum -a 256 -c ARCHIVE.sha256` on Mac or `sha256sum -c ARCHIVE.sha256` on Linux. On Windows compare `(Get-FileHash ./ARCHIVE.zip -Algorithm SHA256).Hash` with the checksum file. Checksums detect corruption; obtain them from this release.

Extract the archive and enter its folder. On Mac/Linux run `sh install-terminal.sh`; on Windows run `./install-terminal.ps1` in PowerShell.

The installers verify extracted files, install without administrator rights, and retain existing data. Default location: `~/.local/bin` on Mac/Linux, `%LOCALAPPDATA%\Overseer\bin` on Windows. Add the directory to your PATH, then run `overseer-tui`. You can also run the extracted executable directly.

For the default Mac/Linux installation, add this line to your shell profile:

```sh
export PATH="$HOME/.local/bin:$PATH"
```

## First session

- Press **F1** for help and **Ctrl+Q** to quit.
- Press **Ctrl+O** to list and choose your installed Ollama models.
- Configure cloud providers and API keys in Settings.
- To connect to an existing daemon: `overseer-tui --remote --url http://127.0.0.1:8080`.

## Preview status

Native builds, 3 terminal unit tests per successful platform, and installation/reinstallation/uninstallation tests passed on Apple Silicon, Linux x64 and Windows x64 CI runners. Mac and Linux also passed a standalone interactive launch/type/quit smoke. Windows interactive acceptance remains unverified.

Intel Mac is excluded because its ONNX dependency build failed. Mac binaries are **not Developer ID signed or notarized**. Existing dependency and launch-readiness findings remain unresolved; this is a preview, not a declaration of general launch readiness. See [BUILD-INFO.json](BUILD-INFO.json) for artifact checksums and verification scope.

## Update and uninstall

For Homebrew, run `brew update` then `brew upgrade overseer`. Uninstall with `brew uninstall overseer`.

For archive installs, rerun the new archive's installer to replace the executable. Uninstall by removing the installed executable. Application data remains intact.

Report problems in this repository's [Issues](https://github.com/Jeccoman/overseer-downloads/issues), including OS, architecture, `overseer-tui --version`, and the error. Remove API keys and personal conversation content before posting.
