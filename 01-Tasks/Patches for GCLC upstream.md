---
type: "[[Task]]"
expected_hours: 2
actual_hours: 2
start_date: 2026-08-26
end_date: 2026-08-26
---
**Objectives:**
- [x] Test changes on upstream gclc before creating pr
- [x] Create pr

Result:
- https://github.com/janicicpredrag/gclc/pull/120
- https://github.com/janicicpredrag/gclc/pull/119
- https://github.com/janicicpredrag/gclc/pull/118

# Execution log:
#### 2026.08.26
- **1.0h** - Test changes on upstream gclc's `master` branch
	- Some of the 'fix' branches' git history contains flatpak related changes as well, so i will need to create a new brench and cherry pick relevant changes
- **1.0h** - Cherry picking and creating pr.