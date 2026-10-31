---
type: "[[Task]]"
expected_hours: 42
actual_hours: 40.7
start_date: 2026-09-19
end_date: 2026-10-05
---
**Description:**
Create a guthub automation that automatically creates packages for a github release.
Types of packages:
- AppImage
- `.deb`
- `.rpm`
- pacman?
- windows installer
- mac?
Entries marked with `?` are not mandatory but would be nice to have.

**Objectives:**
- [x] Get familiar with github actions/workflow
- [x] Get familiar with creating AppImage 
- [x] Create AppImage manually
- [x] Automate AppImage Creation
- [x] Create `deb` package manually
- [x] Automate `deb` package creation
- [x] Create `rpm` package manually
- [x] Automate `rpm` package creation
- [x] Create `pacman` package manually
- [x] Automate `pacman` package creation
- [x] Create and automate windows installer
- [x] Create mac installer
- [x] Test mac installer

**Result**:
- https://github.com/ADG-Foundation/gclc/pull/9
- https://github.com/Vadgoblin/gclc/tree/automated-appimage-build-pure-gh-workflow
- https://github.com/Vadgoblin/gclc/tree/automated-appimage-build-docker-v2

**Links:**
- https://wiki.archlinux.org/title/Creating_packages
- https://wiki.archlinux.org/title/PKGBUILD
- https://wiki.archlinux.org/title/Makepkg

# Execution log:
### 2026.09.18
- `2.0h`: 
	- read upstream's `/.github/workflows/build.yml` 
	- try to build `buildLinuxStatic` manually by hand, but it failed. (`XKB_KEY_dead_belowverticalline`)
### 2026.09.19
- `1.5h`: build `buildLinuxStatic` manually and package it into AppImage
- `1.0h`: try to package gclc as AppImage in a way that it bundles all dependency
- `1.0h`: explore github automation 
### 2026.09.21
- `1.5h`: package gclc without compiling qt using `aqtinstall` but the output AppImage is as big (~32MB) as if i just packed it bundled width qt installed with `apt`.
### 2026.09.22
- `2.5h`:
	- setup `act` to test github acrions locally
	- try to make a gh workflow that caches QT build artifact
	- pulling docker  image catthehacker/ubuntu:full-22.04 takes ages
- `4.0h`:
	- create working gh workflow to build AppImage
	- add caching for qt build
- `1.5h:
	- fix cache id
	- fix result not being uploaded to release page
### 2026.09.23
- `4.0h`
	- try to make smoke test for gh workflo
	- create docker based Flatpak packaging
	- it works locally but fails on github
	- worked on re-run 
### 2026.09.24
- `1.5h`
	- update version of `actions/xx` s
	- replace softprops/action-gh-release@v2 with gh release upload
	- caching on github  is broken, works locally
	- tried but couldn't to fix caching on github 
### 2026.09.25
- `2.0h`: create `deb` and `rpm` package manually
- `1.0h`: fix `deb`'s filename and test it
- `0.5h`: create automated `rpm` building and test `deb` and `rpm`.
- `3.5h`: read about `pacman` packaging
### 2026.09.27
- `1.0h`:
	- read about `pacman` packaging
	- fix CPACK's licence and contact  values
	- create automated `pacman` packaging
- `1.0h`: update scripts and gh workflow to create arm64 appimage as well
- `1.5h`:
	- add arm64 build support for all scripts
	- tried but failed to test arm packages on raspberry pi + distrobox
### 2026.09.28
- `2.5h`:
	- create windows installer
	- setup remote desktop on my other windows machine
	- fix missing icon on installed windows gclc app
### 2026.09.29
- `1.0h`: create mac build
### 2026.09.30
- `0.0h`: 
	- the person I asked to test macos arm64 build reported that couldnt get it to run due to it not being *verified*
	- macos x86_64 build failed on github because waiting for runner timed out
### 2026.10.02
- `1.5h`:
	- removed mac build script
	- noticed that there are 2 `gclc_man.pdf`  in the repo, one of them is older and the older one is packaged inside that executable for in app help
- `3.0h`:
	- remove cache and rebuild everything locally
	- add build script for building manual from latex into pdf
	- update build scripts to include licence, readme, manual,samples, working_example, LaTeX_packages, XML_support
	- fix manual building failes on github actions
	- test github builds
### 2026.10.04
- `1.7h`:
	- Rename dir `package` to `packaging` and update all references to it
	- Smoke test all builds again
	- add missing row from help in `Makefile`
	- Add readme to packaging dir
### 2026.10.04
- `0.0h`: PR got merged