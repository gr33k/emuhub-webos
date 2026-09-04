# Getting Started

EmuHub webOS is the LG TV client for EmuHub. The hosted shell opens your EmuHub
server's library and wheel. The separately packaged native-runtime integration
can launch supported cores while keeping EmuHub as the primary interface.
It is not a standalone console emulator.

This public repository currently contains documentation. Source export,
independent build instructions, and public application releases are pending.
Do not assume that a hosted shell alone installs every native runtime package.

## Installation model

The developer native lane needs a compatible TV, Developer Mode setup, and the
exact shell/helper/runtime/bridge bundle appropriate for the device. Future
public releases must include that manifest, package versions, hashes, storage
requirements, and model-specific restrictions. A store-candidate hosted shell
is not evidence that the native lane is available through the LG store.

The full and low-storage native profiles are different configurations. Native
core inventory is not universal TV compatibility. Missing native prerequisites
must be reported rather than silently opening a different browser core.

## First session

1. Connect the client to your own EmuHub server and verify login/guest access.
2. Check the first-launch video, TV remote navigation, and wheel previews.
3. Pair a gamepad and verify its detected profile before native gameplay.
4. Launch, play, stop safely, and confirm return to the correct wheel.
5. Test a second launch and cleanup after failure before claiming stability.

See [Controller Mapping](Controller-Mapping.md) for the inspected SF30 Pro
profile and the limits of TV-remote input.
