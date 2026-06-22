---
type: "[[Task]]"
expected_hours: 8
actual_hours:
start_date: 2026-06-22
end_date:
---
**Objectives:**
- [ ] Download manifest, build and run it



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