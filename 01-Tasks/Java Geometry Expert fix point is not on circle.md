---
type: "[[Task]]"
expected_hours: 4
actual_hours:
start_date: 2026-09-08
end_date:
---
**Description**
Point is not on the circle.
![196](99-System/Attachments/Pasted%20image%2020260908161822.png)
Line is 0.5px shifted down
![197](99-System/Attachments/Pasted%20image%2020260911160031.png)
Point selector sometimes has (incorrect) offset.
![181](99-System/Attachments/Pasted%20image%2020260911160208.png)

**Objective**
- [x] Find source of the problem
- [x] Fix it

**Results**
- https://github.com/kovzol/Java-Geometry-Expert/pull/54
- https://github.com/kovzol/Java-Geometry-Expert/pull/53

**Execution log:**
`2026.09.08.`
- `2.0h`: source of the problem seems to be casting double to integer instead of rounding as well as using graphics library that only supports integer coordinates
`2026.09.10.`
- `2.0h`: upgrade used graphics api to newer one that supports real number coordinates
- `4.0h`: Little refactoring
`2026.09.11.`
- `2.5h`: fix line 0.5px shifted down, start working on fixin point selector offset
- `0.7h`: fix point selector strange offset