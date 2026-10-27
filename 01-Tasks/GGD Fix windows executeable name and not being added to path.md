---
type: "[[Task]]"
expected_hours: 4
actual_hours: 7.4
start_date: 2026-10-26
end_date: 2026-10-27
---
Description:
The executable's name is `desktop.bay` but should be `Geogebra-Discovery.bat`.
There should be an option to add `Geogebra-Discovery.bat` to the `PATH` env var.

Result:
- https://github.com/kovzol/geogebra/pull/31

# Execution log:
#### 2026.10.26.
- `6.0h`: 
	- fix installed executable name
	- add it to the path automatically
	- make adding it to the path optional
	- try to make creating a desktop icon optional in a way that the check box for this option is on the last page of the installer, however its implementation is really messy and shouldn't this kind of option doesnt belong to the last page anyways.
	- spend a lot of time re-building, installing, uninstalling, the app, checking env vars before and after these installing and removing the app.
#### 2026.10.27.
- `0.9h`:
	- make desktop shortcut creation optional
	- test gh build
- `0.5h`:
	- consult about a cmd window popping up for a fraction of a second when starting GGD from the installer
	- fix it 
	- test the fix