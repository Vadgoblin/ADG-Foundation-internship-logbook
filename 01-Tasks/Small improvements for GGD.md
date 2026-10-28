---
type: "[[Task]]"
expected_hours: 6
actual_hours: 3.4
start_date: 2026-10-27
end_date: 2026-10-28
---
Description:
I was ask to do a few improvements to the GGD windows installer:
- Having 2 `.bat`s, a debug and a non debug one is redundant. If it is being run from terminal, it should log there. If its run by non debug shortcut, it  shouldn't open a terminal for the logs.
- On the installer's "components" page, the middle column is too narrow and text doesn't fit.
- Make the installer available in multiple language.
- Add a screenshot to the welcome page of the installer.

Result:
- https://github.com/kovzol/geogebra/pull/32

# Execution log:
#### 2026.10.27.
- `2.0h`: 
	- don't create debug `.bat` file 
	- remove the component description - waiting for review for the visuals
- `1.4h`:
	- add preview image to the windows installer
	- add multi language support