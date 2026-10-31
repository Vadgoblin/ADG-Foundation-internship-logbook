---
type: "[[Task]]"
expected_hours: 4
actual_hours: 12.4
start_date: 2026-10-27
end_date:
---
**Result**:
- https://github.com/kovzol/geogebra/pull/34

# Execution log:
#### 2026.10.27.
- `1.5h`: start working on packaging script 
- `1.6h`:
	- difficult to do this without a mac machine
	- give up after getting a `The job was not acquired by Runner of type hosted even after multiple attempts`
#### 2026.10.27.
- `4.0h`: backup pc, make a macos vm
- `0.5h`: suffer with "do a small change, commit, release, wait for gh build to finish
- `2.5h`: work on packaging script
#### 2026.10.30.
- `0.6h`: mac vm stopped working - fixing it
- `0.7h`:
	- inside the mac vm, downloading  package from github release page stuck in "preparing to download", curl returns nothing on download url. 
	- Turns out, MTU size was the problem. After changing it top 1400, the download started working again.
	- When i click 'open anyway', when opening an unsigned package, it asks for username and password, but the password field is disabled
	- I didnt do anything on the host and now suddenly its all broken
	- Somehow I lost admin priviladges
	- `sudo spctl --master-disable` disables Gatekeeper
- `0.5h`: get mac build to work
- `0.5h`: also package into `dmg`