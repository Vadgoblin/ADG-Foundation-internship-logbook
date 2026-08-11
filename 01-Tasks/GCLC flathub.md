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


**Useful links:**
- https://docs.flathub.org/docs/for-app-authors/submission
- https://docs.flathub.org/docs/for-app-authors/metainfo-guidelines
- https://doc.qt.io/qt-6/qstylehints.html

**Results:**
- https://github.com/ADG-Foundation/gclc/releases/tag/v2026.08
- https://github.com/flathub/flathub/pull/9611

**Useful commands:**
- `yamllint io.github.ADG_Foundation.gclc.yaml`
- `nix-shell -p desktop-file-utils appstream-glib --run "desktop-file-validate io.github.ADG_Foundation.gclc.desktop && appstream-util validate io.github.ADG_Foundation.gclc.metainfo.xml"`

# Execution log:
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
#### 2026.08.04.
- **2.6h** -
	- Discuss the reasons why submission was rejected
	- Started working on the fix and refactored the build config
		- Implement installation with cmake
		- test it on laptop
- **1.3h** - update flatpak manifest for the updated cmake config
		-  while theme workaround broke 

#### 2026.08.05.
- **2.0h** 
	- Find solution/workaournd for forcing light theme without breaking FileChooser portal
	- Discussing details about where and how to apply changes for the flatpak building

#### 2026.08.06.
- **3.0h**
	- fix dark background when no file is opened in gclc-gui
	- create an install fix but  with as little cnages as possible
	- update and test flatpak manifest 
	- discuss furhter steps with *Zoltán Kovács*
	- fix issues he pointed out
	- update and test flatpak with the merged fixes
	- discussing found issues
		- open help button doesnt do anying on the flatpak build
		- saved file wont be written on disk
- **2.0h**
	- fix *save as* doesnt work *
	- fix help button doesnt work

#### 2026.08.07.
- **2.5h**
	- Creating release for GCLC
	- Create final flatpak manifest
	- Test it:
		- help doesnt open on Raspberry pi, not sure why
	- Submit it
	- Test the fatlapk's build
		- Export doesnt work (same issue as save as)

#### 2026.08.10.
- **3.5h**
	- Fixing *save* (default save location is tmpfs in flatpak)
	- Fixing *export* (doesnt save file unless excension manually added)
	- Testing flatpak build

#### 2026.08.11.
- **2.5h**
	- Update test and submit flatpak manifest
	- Export charses on fedora
	- Save as also chrashes
	-  Fix it.
## Notes:

solution to broken workaround
```
    post-install:
      - mv /app/bin/gclc-gui /app/bin/gclc-gui-bin
      # - install -Dm755 gclc-gui /app/bin/gclc-gui
      - install -Dm755 gclc-gui-wrapper /app/bin/gclc-gui
```