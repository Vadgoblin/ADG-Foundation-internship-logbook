---
type: "[[Task]]"
expected_hours: 12
actual_hours:
start_date: 2026-10-09
end_date:
---
**Description:**
Create a guthub automation that automatically creates packages for a github release.
Types of packages:
- AppImage
- `.deb`
- `.rpm`
- windows installer

**Result**:

**Links:**

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
- `?.?h`
	- Once again i came across the 'fat jar' or 'uber jar' problem. Disabling uber jar breaks some packaging but it makes dist also use fat jar but still keep the other jars and other assets
	- created a separate gradle task to create fat jar and updated related gradle tasks to use it instead of the default jar build witch isnt fat.
	- The file size of the non fat jar still big. It contains all the java resources after all, but `gradlew installDist` also copies thees files to the output dir next to the `jgex` executable.
	- `src/main/java/wprover/GExpert.java` line 830 `void addDirectory(JMenu menu, String resourceDir)` -> looks like the application can handle loading files from jar


**Other:**

|                                                           | "runnable" jar | deb  | rpm  | AppImage | dist install |
| --------------------------------------------------------- | -------------- | ---- | ---- | -------- | ------------ |
| fat jar                                                   | 17.2           | 65.6 | 65.9 | 64.1     | 42.4         |
| non fat jar (some of the builds are broken)               | 11.3           | 60.4 | 60.7 | 58.9     | 36.5         |
| non fat jar without copying files that are already in jar |                | 57.8 | 57.8 |          |              |

