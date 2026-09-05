---
type: "[[Task]]"
expected_hours: 42
actual_hours:
start_date: 2026-09-03
end_date:
---
**Description**
When running JGEX in cheerpj, the save and load doesnt work as expected. It opens a window inside the containerized environment and only the files within this container visible. Expected behavior: Save and load opens a native window on the host machine with access to the files in the host. 
The task is to implement the expected behavior. 

**Objective**
- [x] Setup dev enviorment
- [x] Read `cheerpj` docs.
- [ ] Implement feature.

**Results**
- https://github.com/Vadgoblin/Java-Geometry-Expert/tree/fix-cheerpj-save-load
- https://github.com/Vadgoblin/jgex-web

**Links**
- https://cheerpj.com/docs/overview

**Execution log:**

`2026.09.02.`
- `2.0h` - Forking jgex repo, creating a repo for 'web' part of the program, creating helper scripts to run build `jgex`, copy the `.jar` to the target location and separate script for running a local web server. Attempted to run open a host native file chooser from java(web) but failed. I should read the docs.

`2026.09.03.`
- `1.0h` - Read `cheerpj` docs.
- `1.0h` - Implement communication between java and javascript

`2026.09.04`
- `3.5h` - Implement load, import, start working on save.
- `2.5h` - Implement save, and some of the 'save as'
- `1.0h` - Deploy on vps, configure ssl
- `1.0h` - Continue working on `export to ps`, but getting strange exception `java.lang.ClassCastException` on web but not on native java