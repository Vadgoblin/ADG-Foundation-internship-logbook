---
type: "[[Task]]"
expected_hours: 16
actual_hours: 18.8
start_date: 2026-06-02
end_date: 2026-06-14
---
**Objectives:**
 - [x] Read `flatpack` documentation.
 - [x] Create a `Hello world` `flatpack` package.
 - [x] Read `flathub` documentation.
 - [x] Update flatpak yaml.

Execution Log:

### 2026.06.13.
- **0.8h** Read flathub documentation
### 2026.06.12.
- **1.0h** Test it and fix x11 fallback. 
- **0.3h** Trying other java based flatpak packaged programs to see how they behave on wayland and check their flatpak manifest.
	- jetbrains' idea has the same 'window size being ignored and rendered at incorrect resolution until application becomes a floating window in sway wm' so its a problem with the java's wayland support and not with JGE.
- **0.3h** Build and run flatpak on a different machine (fedora, kde, x86-64)
	- doesnt have the 'window size being ignored...' issue under kde
- **0.7h** Set up arm64 environment for testing arm support.
- **0.4h** Update manifest with arm64 support and test it on a raspberry pi.
  - **0.6h** [JGE flatpak size optimalization](03-Docs/JGE%20flatpak%20size%20optimalization.md)
- **0.7h** Find only needed java libraries with `jdeps`, clean up manifest
### 2026.06.10.
- **0.7h** Trying to pump jdk version in flatpak.
- **2.5h** Get the source to work on wayland natively.
	- Wayland works using command `./gradlew run` with  `JetBrains`' java runtime and `-Dawt.toolkit.name=WLToolkit`, but its buggy: (under sway wm) it renders at incorrect resolution until resize and `exit` hangs
	- having difficulties reproducing successful `./gradlew  --no-daemon  installDist`
	- `./gradlew run` doesnt work anymore with `JetBrains`' java runtime, i dont know why
- **1.8h** Update flatpak yaml so app can run with native wayland
	- Flatpak building takes ages
	- Run out of space on my machine
	- Managed to get it to work with wayland but it doesnt work with x11

### 2026.06.03.
- **2.3h** Reading `flatpak` documentation
- **0.5h** Build current version of Java Geometry Expert.
	- Windows resize doesnt work properly under sway/xwayland.
- **1.0h** Trying to pump jdk version in flatpak.

### 2026.06.02.
* **5.2h** - Reading flatpak documentation