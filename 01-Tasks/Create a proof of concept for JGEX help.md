---
type: "[[Task]]"
expected_hours: 2
actual_hours: 2.3
start_date: 2026-10-24
end_date: 2026-10-24
---
**Description:**
The current implementation opens the help bundled into the package with a web-browser installed on the host machine. There are two problems with that.
- The help is in the `resources` java directory, so when a `.jar` is created, it is being copied into the `.jar`. The issue is that external programs can't read files from a jar. The 'solution' to this was to copy the help files next to the jar, so external programs can access it. It results in it being packaged twice: inside the `.jar` and next to it in the form of regular files.
- If the external browser is installed with a flatpak package, flatpak's sandbox will only give access to the file, that was opened. That is `index.html`. Access to all other files is blocked, making the help unusable,
My idea to solve this problem was to have an in-app help. 
This is a proof of concept for it.

**Results**:
- [ https://github.com/kovzol/Java-Geometry-Expert/pull/62](https://github.com/Vadgoblin/Java-Geometry-Expert/tree/rework-help)

# Execution log:
#### 2026.10.24.
- `2.3h`: -