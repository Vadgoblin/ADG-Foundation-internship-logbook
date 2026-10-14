---
type: "[[Task]]"
expected_hours: 32
actual_hours:
start_date: 2026-10-14
end_date:
---
**Objectives:**
- [x] clone repo, create new branch, get the project to build
- [ ] create  automated packaging for `.deb` 
- [ ] create  automated packaging for `.rpm` 
- [ ] create  automated packaging for `.pacman` 
- [ ] create  automated packaging for `.AppImage` 
- [ ] create  automated packaging for  Windows

Result:
- 

# Execution log:
#### 2026.10.14
- `1.5h`:
	- Having trouble getting it to build and run
	- Javapackager needs newer java but ggd needs older, so i need to find an other way to package the application
- `2.5h`:
	- read https://wiki.debian.org/MakeAPrivatePackage
	- read https://wiki.debian.org/Packaging/Intro
	- read https://wiki.debian.org/action/show/Packaging/BinaryPackage
	- read https://wiki.debian.org/action/show/Packaging/SourcePackage
	- read https://wiki.debian.org/Java/Packaging
	- Start working on `deb` packaging 