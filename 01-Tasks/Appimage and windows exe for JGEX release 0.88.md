---
type: "[[Task]]"
expected_hours: 10
actual_hours: 19.8
start_date: 2026-09-15
end_date: 2026-09-16
---
**Description:**
Create an Appimage and a windows exe for the latest (0.88) release of `Java Geometry Expert`

**Objectives:**
- [x] Read Appimage docs
- [x] Make appimage
- [x] Make windows executeable

**Result:**
- https://github.com/kovzol/Java-Geometry-Expert/pull/55
- `AppImage`
- windows installer `exe`

**Links:**
- https://docs.appimage.org/index.html

# Execution log:
### 2026.09.14:
- `4.5h` read Appimage docs
### 2026.09.15:
- `1.5h`: read Appimage docs
- `1.5h`: extract previous release's appimage and explore it structure, create an app image from the new build
- `0.5h`: strip jdk to achieve smaller AppImage size
- `2.3h`: 
	- Try to make `AppImage` using   `./gradlew package` but that fails with 404 error because `javapackager` is too old. Its unmaintained so no update.
	- Try to make `AppImage` using `de.infolektuell.jpackage` with the command `./gradlew appImage` but that fails when running `jdeps`. (Stripping jdk)
	- Notice the config for making 'fat jars' in build.gradle. Turns out, `./gradlew installDist` make a fat jar for the application (which includes all depencency) + puts all dependency next to it as separate files as well.
	- Investigate whether or not fat jar is needed for `deb` and `rpm` package creation. I suspected that its needed, but (unless i messed up) it works without it. There is a size comparison table below.
### 2026.09.16:
- `0.5h`: test non fat jar based `.deb` installer
- `1.0h`: create `.exe` installer on windows
- `1.5h`: try to figure out why my built takes more space
	- It seems like the resources are both inside the `jar` and copied to `dist` output. Some part of the code uses the files inside the `jar` and some the files on the disk.
- `2.0h` 
	- fix typo
	- improve variable and method naming
	- update hardcoded date 
	- figure out why the `help` so flaky
	- create final `AppImage`

---
# Notes:

Commands:
- `wget -O appimagetool https://github.com/AppImage/appimagetool/releases/latest/download/appimagetool-x86_64.AppImage`
- `./appimagetool Java-Geometry-Expert.AppDir Java-Geometry-Expert.AppImage`
- `curl -L -o openjdk21.tar.gz "https://api.adoptium.net/v3/binary/latest/21/ga/linux/x64/jdk/hotspot/normal/eclipse"`
- `mkdir -p build-jdk && tar -xzf openjdk21.tar.gz -C build-jdk --strip-components=1`
```
 ./build-jdk/bin/jlink \
                               --add-modules java.base,java.datatransfer,java.xml,java.prefs,java.desktop,java.logging,java.security.sasl,java.naming,java.transaction.xa,java.sql \
                               --strip-debug \
                               --no-man-pages \
                               --no-header-files \
                               --compress=zip-6 \
                               --output my-custom-runtime
```


jre in the reference appimage:
```
JAVA_VERSION="15.0.10"
MODULES="java.base java.datatransfer java.xml java.prefs java.desktop java.logging java.security.sasl java.naming java.transaction.xa java.sql"
```

output of `./gradlew package` with and without fat jar:

|             | jar      | deb  | rpm  |
| ----------- | -------- | ---- | ---- |
| non fat jar | 11.3<br> | 60   | 60.2 |
| fat jar     | 17.2     | 65.2 | 65.5 |
