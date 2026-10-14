---
type: "[[Task]]"
expected_hours: 4
actual_hours: 1.6
start_date: 2026-10-14
end_date: 2026-10-14
---
**Objectives:**
- [x] Figure out "where the problem comes from"
- [x] Fix it

**Result**:
- https://github.com/kovzol/Java-Geometry-Expert/pull/59/
# Execution log:
#### 2026.10.14.
- `1.6h`:
	- When gclc is built and run locally (`gradle run`), the encoding is ok
	- When running `jgex.jar` from the web build built by  gh, the encoding is ok
	- gh workflow  started to fail
	- after git reset and force pushing, gh workflow works again