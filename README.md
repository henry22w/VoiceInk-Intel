# VoiceInk Intel

### VoiceInk 2.22 for Intel Macs (Unofficial)

I wanted to try [VoiceInk](https://github.com/Beingpax/VoiceInk) on my older Intel MacBook Pro, but I couldn't find an official Intel Mac download. Since VoiceInk's source code is available under GPLv3, I decided to try compiling it myself.

After resolving several build errors and adjusting two dependencies, I successfully compiled and ran **VoiceInk 2.22** on my Mid-2014 MacBook Pro running macOS Sequoia 15.7.5 through OpenCore Legacy Patcher.

I'm sharing this **unofficial, experimental Intel (x86_64) build** so other people with older Macs can try it without having to compile the application themselves.

**I've only tested it on my own Mac. Compatibility with other Intel Macs is not guaranteed.**

## Build Information

| Item | Details |
|---|---|
| VoiceInk version | 2.22 |
| Build number | 224 |
| Upstream source commit | `19546d2a` (October 30, 2026) |
| Xcode version | 26.3 |
| Architecture | Intel (x86_64) |
| Code signing | Ad-hoc, not notarized by Apple |

### Tested Hardware and Software

- **Computer:** 15-inch MacBook Pro (Mid-2014)
- **Graphics:** Intel Iris Pro
- **Operating system:** macOS Sequoia 15.7.5
- **OpenCore Legacy Patcher:** 2.4.1

## What I Changed

I compiled the original VoiceInk source code using its `make local` build process.

To resolve compilation errors, I adjusted two Swift package dependencies:

- `mlx-swift` pinned to version `0.31.4`
- `mlx-swift-lm` changed to version `3.31.4`

These changes allowed VoiceInk to compile successfully using my installed version of Xcode.

However, they do not make every Apple Silicon-specific feature compatible with Intel hardware.

The corresponding source code, including the dependency changes, will be provided in this repository's `intel-v2.22` branch and associated release tag.

## What I Tested

I successfully launched VoiceInk and tested basic speech-to-text transcription using:

- **Whisper Tiny**
- **Parakeet V3**

Both models worked on my Intel MacBook Pro.

However, local transcription was noticeably slower than cloud-based transcription services.

In my limited testing, Whisper Tiny performed faster than Parakeet V3.

Other transcription models, cloud integrations, AI enhancement, and advanced features have not been thoroughly tested.

## Known Limitations

- This is an experimental build tested on only one Intel Mac.
- Other Intel Macs and macOS versions may have compatibility issues.
- Local AI transcription can be slow on older Intel hardware.
- Features requiring Apple Silicon may not work.
- Local builds do not include iCloud dictionary synchronization.
- Automatic updates are not available. New versions must be compiled separately.
- The application is ad-hoc signed and not notarized by Apple.
- macOS may display security warnings when opening the application.
- This is not an official VoiceInk release, and I cannot guarantee future updates or technical support.

## Download and Installation

1. Open the **Releases** section of this GitHub repository.
2. Download `VoiceInk-v2.22-build224-Intel.zip`.
3. Extract the ZIP file.
4. Move `VoiceInk.app` into your Applications folder.
5. Launch VoiceInk and complete the initial setup.
6. Review and grant the necessary macOS permissions.
7. Download your preferred transcription model and test a short recording.

### macOS Security Warning

Because this application is not notarized by Apple, macOS may prevent it from opening automatically.

If you trust the downloaded application, you may be able to authorize it through:

**System Settings → Privacy & Security → Open Anyway**

Only bypass macOS security warnings for applications you trust.

### SHA-256 Checksum

89bdc446623be86b8b929d150dc3566071d0510480711b6bd1c661c929be84ce

You can use this checksum to verify the integrity of your downloaded ZIP file.

## Source Code and License

**Original project:** https://github.com/Beingpax/VoiceInk

**Original developer:** Pax and the VoiceInk contributors

**License:** GNU General Public License v3.0 (GPLv3)

This unofficial build is based on the original VoiceInk source code.

The complete corresponding source code, including the dependency changes and applicable license notices, must be made available with the release in accordance with the GPLv3 license.

All credit for the original VoiceInk application belongs to its developer and contributors.

This Intel build is an independent community effort and is not affiliated with, sponsored by, or endorsed by the original developer.

## Support This Intel Build

If you find my Intel build helpful and would like to support my efforts, you can make a optional voluntary donation of any amount through Ko-fi: **[Support VoiceInk Intel on Ko-fi](https://ko-fi.com/henryyip1)**

I spent time compiling, troubleshooting, and testing VoiceInk to make it accessible to people still using older Intel Macs.

**No payment or donation is required to download or use this GPLv3 build.**

## Feedback and Compatibility Reports

If you try this build on another Intel Mac, I would appreciate your feedback.

Please open a GitHub Issue and include:

- Your Mac model and processor
- Your macOS version
- Whether you're using OpenCore Legacy Patcher
- Which transcription model you tested
- Whether dictation works
- Any error messages or performance issues

This information will help determine which Intel Macs are compatible with this experimental build.
