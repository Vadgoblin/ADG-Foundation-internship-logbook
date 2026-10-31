---
type: "[[Task]]"
expected_hours: 4
actual_hours: 4.8
start_date: 2026-10-21
end_date: 2026-10-24
---
**Description:**
Create a github wokflow to automatically create mac build on release.

Result:
- https://github.com/ADG-Foundation/gclc/pull/11

# Execution log:
#### 2026.10.21.
- `0.4h`: create script (building tooks hours - building timed out)
#### 2026.10.22.
- `0.7h`: somehow get build to work
- `1.5h`: fix `gclc-gui` crashes on start
- `1.2h`:
	- add safety check so macos build script can only run on mac
	- refactor build script
	- fix zip (all contents are in zip root)
	- accidentaly releasing from wrong branch
	- getting confused because of working on [Web build for Geogebra Discovery](01-Tasks/Web%20build%20for%20Geogebra%20Discovery.md) simultaneously 
- `1.0h`:
	- bump github action version
	- fix inconsistent github action names
	- fix missing icon
	- patiently wait for github to build the package and for [Zoltán Kovács](Zoltán%20Kovács) to test it.
#### 2026.10.24.
- `0.0h`: pr got merged