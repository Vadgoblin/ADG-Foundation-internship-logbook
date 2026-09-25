---
type: "[[Task]]"
expected_hours: 42
actual_hours:
start_date: 2026-09-19
end_date:
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

**Objectives:**
- [x] Get familiar with github actions/workflow
- [x] Get familiar with creating AppImage 
- [x] Create AppImage manually
- [x] Automate AppImage Creation
- [x] Create `deb` package manually
- [x] Automate `deb` package creation
- [x] Create `rpm` package manually
- [x] Automate `rpm` package creation
- [ ] Create `pacman` package manually
- [ ] Automate `pacman` package creation

Result:
- https://github.com/Vadgoblin/gclc/tree/automated-appimage-build-pure-gh-workflow
- https://github.com/Vadgoblin/gclc/tree/automated-appimage-build-docker-v2
- https://github.com/Vadgoblin/gclc/tree/__manual_deb_rpm_packaging

# Execution log:
#### 2026.09.18
- `2.0h`: 
	- read upstream's `/.github/workflows/build.yml` 
	- try to build `buildLinuxStatic` manually by hand, but it failed. (`XKB_KEY_dead_belowverticalline`)
#### 2026.09.19
- `1.5h`: build `buildLinuxStatic` manually and package it into AppImage
- `1.0h`: try to package gclc as AppImage in a way that it bundles all dependency
- `1.0h`: explore github automation 
#### 2026.09.21
- `1.5h`: package gclc without compiling qt using `aqtinstall` but the output AppImage is as big (~32MB) as if i just packed it bundled width qt installed with `apt`.
#### 2026.09.22
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
#### 2026.09.23
- `4.0h`
	- try to make smoke test for gh workflo
	- create docker based Flatpak packaging
	- it works locally but fails on github
	- worked on re-run 
#### 2026.09.24
- `1.5h`
	- update version of `actions/xx` s
	- replace softprops/action-gh-release@v2 with gh release upload
	- caching on github  is broken, works locally
	- tried but couldn't to fix caching on github 
#### 2026.09.25
- `2.0h`: create `deb` and `rpm` package manually
- `1.0h`: fix `deb`'s filename and test it
- `0.5h`: create automated `rpm` building and test `deb` and `rpm`.
- `3.5h`: read about `pacman` packaging