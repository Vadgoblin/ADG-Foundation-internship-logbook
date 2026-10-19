---
type: "[[Task]]"
expected_hours: 32
actual_hours:
start_date: 2026-10-14
end_date:
---
**Objectives:**
- [x] clone repo, create new branch, get the project to build
- [x] create  automated packaging for `.deb` 
- [x] create  automated packaging for `.rpm` 
- [x] create  automated packaging for `.pacman` 
- [x] create  automated packaging for `.AppImage` 
- [x] create  automated packaging for  Windows

Result:
- https://github.com/kovzol/geogebra/pull/28

# Execution log:
#### 2026.10.14.
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
#### 2026.10.15.
- `2.7h`: work on deb packaging
- `4.2`:
	- finish automated deb packaging
	- test created packages (both x86_64 and aarch64)
	- create github workflow
	- aarch64 build fails on gh workflow
	- auto packaged `.deb` package is way larger then the linux zip in previous upstream releases - looks like my package includes unneeded jars (for different OSes  and different architectures)
	- fix file size
	- re-test `.deb`s
	- read https://docs.fedoraproject.org/en-US/package-maintainers/Packaging_Tutorial_1_banner/
	- read https://docs.fedoraproject.org/en-US/package-maintainers/Packaging_Tutorial_2_GNU_Hello/
- `2.5h`:
	- build `rpm` by hand
	- write rpm packaging script
#### 2026.10.16.
- `2.5`:
	- fix filenames in `.deb` packaging script
	- fix filename, permission and hardcoded version number in `.rpm` packaging script
	- smoke test the gh build
	- start making pacman packaging script
- `3.4h`: 
	- finish  pacman packaging script
	- test created package
	- create github workflow for automated pacman packaging
	- pacman and rpm workflow wails on gh
	- fix workflow breaking bug, fix minor stuff like missing "-discovery" postfix in some file names
	- start making AppImage packaging script
- `2.4h`:
	- finish AppImage packaging script
	- test AppImage build
	- create gh workflow for AppImage packaging
	- set correct licence
	- minor fixes
#### 2026.10.19.
- `4.1`: start working on windows installer build script
- `3.2`: finish windows installer build script
- `0.6`:
	- fix rpm packaging fails
	- test gh's build