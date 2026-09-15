---
type: "[[Task]]"
expected_hours: 10
actual_hours:
start_date: 2026-09-15
end_date:
---
**Description:**
Create an Appimage and a windows exe for the latest (0.88) release of `Java Geometry Expert`


**Objectives:**
- [x] Read Appimage docs
- [ ] Make appimage
- [ ] Make windows executeable

**Links:**
- https://docs.appimage.org/index.html

**Result:**
- 

# Execution log:
#### 2026.09.14:
- `4.5h` read Appimage docs
#### 2026.09.15:
- `1.5h`: read Appimage docs
- `1.5h`: extract previous release's appimage and explore it structure, create an app image from the new build
- `0.5h`: strip jdk to achieve smaller AppImage size
- `2.3h`: 
	- Try to make `AppImage` using   `./gradlew package` but that fails with 404 error because `javapackager` is too old. Its unmaintained so no update.
	- Try to make `AppImage` using `de.infolektuell.jpackage` with the command `./gradlew appImage` but that fails when running `jdeps`. (Stripping jdk)
	- Notice the config for making 'fat jars' in build.gradle. Turns out, `./gradlew installDist` make a fat jar for the application (which includes all depencency) + puts all dependency next to it as separate files as well.
	- Investigate whether or not fat jar is needed for `deb` and `rpm` package creation. I suspected that its needed, but (unless i messed up) it works without it. There is a size comparison table below.  



**Other:**
output of `./gradlew package` with and without fat jar:

|             | jar      | deb  | rpm  |
| ----------- | -------- | ---- | ---- |
| non fat jar | 11.3<br> | 60   | 60.2 |
| fat jar     | 17.2     | 65.2 | 65.5 |
