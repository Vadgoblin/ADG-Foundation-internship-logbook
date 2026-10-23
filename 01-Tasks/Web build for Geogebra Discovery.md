---
type: "[[Task]]"
expected_hours: 4
actual_hours:
start_date: 2026-10-21
end_date:
---
**Description:**
Create a github wokflow to build the web version of Geogebra Discovery automatically on release and upload it to the release page.

Result:
- https://github.com/kovzol/geogebra/pull/29

# Execution log:
#### 2026.10.21.
- `1.6h`:
	- figure out how to run https://github.com/kovzol/geogebra-discovery
	- write packaging script
	- iteratively fix build script
	- test it
#### 2026.10.22.
- `1.2h`:
	- fix zip contains nested directories
	- fix names in github workflows
	- test if removing `-Pgdraft` results in any significant change
	- test gh workflow's artifact
- `0.5h:`  fix files in web build's zip are in the root
- `0.3`: 
	- re-run gh workflow because i disable wrong one due to accidentally swapped names 
	- fix name swap