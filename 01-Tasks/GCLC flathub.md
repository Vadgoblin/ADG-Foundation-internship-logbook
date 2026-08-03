---
type: "[[Task]]"
expected_hours: 8
actual_hours:
date_started: 2026-08-01
date_completed:
---
**Objectives:**
- [x] Install and explore GCLC
- [x] Create flatpak manifest
- [x] Submit
- [ ] Fix issues


**Links:**
- https://docs.flathub.org/docs/for-app-authors/submission
- https://docs.flathub.org/docs/for-app-authors/metainfo-guidelines

**Useful commands:**
- `yamllint io.github.ADG_Foundation.gclc.yaml`
- `nix-shell -p desktop-file-utils appstream-glib --run "desktop-file-validate io.github.ADG_Foundation.gclc.desktop && appstream-util validate io.github.ADG_Foundation.gclc.metainfo.xml"`
- 

Execution log:

#### 2026.08.01
- **0.5h** - Install and try `gclc` 
- **1.5h** - Create a minimal, working flatpak manifest
- **1.0h** - Trying to fix dark theme
	- `--env=QT_QPA_PLATFORMTHEME=generic` fixes colors but breaks *File Chooser Portal*  
- **2.0h** - Trying to fix dark theme issue without braking the *File Chooser Portal* 
- **2.0h** - Create `metainfo`, `desktop` files. Trying to upscale icon.
- **1.5h** - 
	- Add final icons
	- refine metadata
	- test it on laptop
	- create screenshots and video
- **0.3h** - add branding color

#### 2026.08.02.
- **1.0h** - Preparing for submitting
	- Read submission requirements
	- Address linter errors
	- Discovering that the used appid might be incorrect
- **0.3h** - Attempted to test it on raspberry pi but it ships legacy software

#### 2026.08.03.
- **2.2h** - Preparing for submitting
	- updating urls to point to the ADG-Foundation fork
	- fixing linter errors
		- screenshot has padding and too big
		- format yaml
	- test if it still builds
	- create a helper `Makefile` for building, linting and running a flatpak
	- test it on arm64 (raspberry pi)
- **1.0h** -
	- remove leftover commends from `dekstop` file
	- update source
	- submit
	- figure out why automated test failed