Standalone Overseer terminal preview for Apple Silicon Mac, Linux x64 and Windows x64. Product source remains private.

Install on supported Mac/Linux systems:

```sh
brew install Jeccoman/tap/overseer
overseer-tui
```

For manual or Windows installation, download the matching archive and checksum, verify, extract, and run its included installer. Models are separate. Press F1 for help, Ctrl+O for installed Ollama models, and Ctrl+Q to quit.

Native builds and package install/reinstall/uninstall, invalid-argument and corruption-rejection checks passed for these three targets. Mac and Linux interactive launch/type/quit smoke passed. Windows interactive acceptance is unverified.

Intel Mac is excluded because its ONNX dependency build failed. Mac downloads are not Developer ID signed/notarized. Existing dependency and launch-readiness findings remain unresolved. This is a preview.

SHA256SUMS.txt and BUILD-INFO.json provide checksums and verification scope. See the repository README for installation instructions.
