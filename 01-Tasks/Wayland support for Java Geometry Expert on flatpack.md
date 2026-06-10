---
type: "[[Task]]"
status: "#task/active"
expected_hours: 16
actual_hours: 0
start_date: 2026-05-28
end_date:
---
**Objectives:**
 - [x] Read `flatpack` documentation.
 - [x] Create a `Hello world` `flatpack` package.
 - [ ] Read `flathub` documentation.
 - [ ] Update flatpak yaml.

Execution Log:

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