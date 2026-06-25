---
type: "[[Task]]"
expected_hours: 8
actual_hours:
start_date: 2026-06-22
end_date:
---
**Objectives:**
- [x] Download manifest, build and run it
- [ ] Update manifest 



Execution log:
### 2026.06.22.
- **0.3h** - Download manifest and get it to run
	- Under sway, trough xwayland, the programs window is pure while. Tooltips appear if i hover the mouse over them.
- **0.2h** - Modifying the manifest similarly to Java Geometry Expert, it work on wayland at first try
	- Doesn't have the same windows size and freeze on quit bug as in [Wayland support for Geogebra discovery on flatpack](01-Tasks/Wayland%20support%20for%20Geogebra%20discovery%20on%20flatpack.md)
- **1.4h** - Testing it on different machines
	- On x86_64/fedora laptop, the flatpak failes to build
	- It failes with reverted manifest as well for some reason.
	- It fails on arm64/rasberrypios
	- raspberry pi runs out of disk storage
	- having trouble building flatpak due to raspberry pi os (apt) shipping old package verions
- **1.0h** - Can't reproduce building error. It might be invalid cache.
- **0.3**h - Trying to figure out the source of mouse icon glitch
- **1.0h** - Trying to build geogebra from source for figuring out what java deps is has from jre and what is safe to strip out.

### 2026.06.23.
- **1.4h** - Trying to find required JRE modules for stripping.
- **1.3h** - Build with normal (non stripped) JDK and test it
	- `3D graphic` doesn't work under wayland


[3d error stack trace](02-Docs/Geogebra%20discovery%203d%20error%20stack%20trace.md)
## Random notes:
### Flatpak bundle size:
old manifest: 107.7
new with stripped jbrsdlk (missing deps): 100.1
new with jbr: 164

### Mouse icon glitch:
![](99-System/Attachments/Pasted%20image%2020260622212541.png)