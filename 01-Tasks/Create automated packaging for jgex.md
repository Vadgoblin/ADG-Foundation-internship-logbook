---
type: "[[Task]]"
expected_hours: 12
actual_hours: 15.4
start_date: 2026-10-09
end_date: 2026-10-13
---
**Description:**
Create a guthub automation that automatically creates packages for a github release.
Types of packages:
- AppImage
- `.deb`
- `.rpm`
- windows installer

**Result**:
- https://github.com/kovzol/Java-Geometry-Expert/pull/58

#### 2026.10.09.
- `2.0h`:
	- take a look ad the code, build it manually, check previous manual AppImage and the commands i used to create it
	- start writing build script
- `3.5h`:
	- The app version is hardcoded at 2 places: `Version.java` and `build.gradle`. This hardcoding makes auto packaging impossible, so i fixed it by injecting version as a parameter when running `gradlew`
	- arm64 packaging is very slow
	- arm64 `appimagetool` doesnt want to run in arm64 emulated docker container for same reason
	- complete AppImage build script, push it to gh, workflow runs on release
	- test gh's builds
- `2.7h`
	- Once again i came across the 'fat jar' or 'uber jar' problem. Disabling uber jar breaks some packaging but it makes dist also use fat jar but still keep the other jars and other assets
	- created a separate gradle task to create fat jar and updated related gradle tasks to use it instead of the default jar build witch isnt fat.
	- The file size of the non fat jar still big. It contains all the java resources after all, but `gradlew installDist` also copies thees files to the output dir next to the `jgex` executable.
	- `src/main/java/wprover/GExpert.java` line 830 `void addDirectory(JMenu menu, String resourceDir)` -> looks like the application can handle loading files from jar
	- fixed `gradle` config to remove packaging things twice including java dependencies and resources

#### 2026.10.10.
- `1.5h`:
	- test builds with non fat jar
	- create build script for `rpm` and `deb`
- `3.5h`
	- cannot set dependencies for created `rpm` and `deb` packages
	- `rpm` build freezes when 'About' is clicked 
	- turns out there is update for java packager, but the way it needs to be pulled is changed
	- getting `Error: Module jgex.runnable contains package org.xml.sax.ext, module java.xml exports package org.xml.sax.ext to jgex.runnable`  with new java packager
	- update gh workflow to not use helper scripts from `packaging`
	- create gh workflow for building windows installer
	- test windows build
	- create gh workflow for building web version of jgex
	- test web build
	- help is broken. Not putting the files next to the executeable is an issue, so i updated the `gradle` config to copy them to the appropriate place, but even with this, it still either doesnt open at all, or only the main page works

#### 2026.10.12.
- `1.3h`: 
	- fix reported problem (graph window wont open)
	- test it
#### 2026.10.12.
- `0.9h`:
	- Pr got merged
	- Some discussion about the windows encoding bug and I helped setting up the github page for [Fix online help of JGEX](01-Tasks/Fix%20online%20help%20of%20JGEX.md).

**Other:**

|                                                           | "runnable" jar | deb  | rpm  | AppImage | dist install |
| --------------------------------------------------------- | -------------- | ---- | ---- | -------- | ------------ |
| fat jar                                                   | 17.2           | 65.6 | 65.9 | 64.1     | 42.4         |
| non fat jar (some of the builds are broken)               | 11.3           | 60.4 | 60.7 | 58.9     | 36.5         |
| non fat jar without copying files that are already in jar |                | 52.4 | 54.2 | 52.2     | 17.3         |

