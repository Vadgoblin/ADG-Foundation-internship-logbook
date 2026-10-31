---
type: "[[Task]]"
expected_hours: 32
actual_hours: 35.7
start_date: 2026-06-24
end_date:
---
**Objectives:**
- [x] Read Nix doc
- [x] Install Nix
- [x] Create nix package

**Links:**
- https://nix.dev/manual/nix/2.28/
- https://nixos.org/guides/nix-pills/
- https://github.com/NixOS/nixpkgs/blob/master/CONTRIBUTING.md
- https://github.com/NixOS/.github/blob/master/CODE_OF_CONDUCT.md
- https://github.com/NixOS/nixpkgs/blob/master/maintainers/README.md
- https://github.com/NixOS/nixpkgs/blob/master/pkgs/README.md
- https://github.com/NixOS/nixpkgs/blob/master/pkgs/by-name/README.md

# Execution log:
### 2026.06.24. 
- `0.7h`: Read docs
### 2026.06.25. 
- `4.2h`: Read docs
- `0.2h`: Install nix
### 2026.06.26. 
- `2.0h`: Read docs
- `1.0h`: Read docs
### 2026.07.01
- `3.2h`: Read manual
### 2026.07.02
- `5.2h`: Read nix pills
### 2026.07.03
- `4.0h`: Read nix pills and `CONTRIBUTING.md` of `nixpkgs`
### 2026.07.21.
- `4.0h`: Read `CODE_OF_CONDUCT`, `maintainers/README.md`,`pkgs/README.md`, `pkgs/by-name/README.md`
### 2026.07.22.
- `2.5h`:  [Writing simple (hello world) nix packages](https://github.com/Vadgoblin/learn_nix_java_packaging/). 
- `2.5h:` Working on nix packaging `jgex`
	- Preferences and other pop up windows are empty
### 2026.07.23.
- `0.6h`:
	- Installing nix on laptop
	- testing build on laptopn
	- finding solution/workaround to the 'empty window' problem 
- `2.0h`:
	- populate `meta` attributes
	- generating and installing `.desktop` file and installing icons
	- installing nixos to to test package
		- vm is slow
- `2.0h`:
	- making sure my nix config complies with `nixpkgs` rules
	- `git fetch` hangs
	- overthinking minor details
### 2026.07.24.
- `1.6h`:
	- installing nix on raspberry pi
	- testing package on rapsberry pi (arm64)
	- [creating PR](https://github.com/NixOS/nixpkgs/pull/545159), final double checking things 
	- troubleshooting github check pipeline faliure
### Waiting for review/merge.

---

## Notes
- `nix-build -A <pkg_name>` at the root of a local `nixpkgs` repo
- validate `.desktop` files with `nix-shell -p desktop-file-utils --run "desktop-file-validate result/share/applications/*.desktop"`
- format nix file `nixfmt pkgs/by-name/yo/your-package-name/package.nix`

Preferences and other pop up windows are empty:
![](99-System/Attachments/Screenshot_2026-07-22_17-48-30.png)