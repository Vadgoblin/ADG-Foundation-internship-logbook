
| old/pre wayland                | 57M  |
| ------------------------------ | ---- |
| JBR with JCEF                  | 256M |
| JBR with JCEF, openjdk removed | 223M |
| JBR vanilla, openjdk removed   | 115M |
| JBRSDK stripper, ojdk removed  | 64M  |
| JBRSDK stripper                | 97M  |

get actually needed libraries:
`./jdeps --ignore-missing-deps --print-module-deps path/to/file.jar`