<!-- QueryToSerialize:  

TABLE WITHOUT ID
"[" + file.name + "](" + replace(file.path, " ", "%20") + ")" AS "Link",
	expected_hours AS "Expected", 
	actual_hours AS "Actual"
FROM "01-Tasks"
SORT expected_hours DESC

-->
<!-- SerializedQuery: TABLE WITHOUT ID "[" + file.name + "](" + replace(file.path, " ", "%20") + ")" AS "Link", expected_hours AS "Expected", actual_hours AS "Actual" FROM "01-Tasks" SORT expected_hours DESC -->

| Link                                                                                                                                   | Expected | Actual |
| -------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------ |
| [Wayland support for Java Geometry Expert on flatpack](01-Tasks/Wayland%20support%20for%20Java%20Geometry%20Expert%20on%20flatpack.md) | 16       | 18.8   |
| [Wayland support for Geogebra discovery on flatpack](01-Tasks/Wayland%20support%20for%20Geogebra%20discovery%20on%20flatpack.md)       | 8        | \-     |

<!-- SerializedQuery END -->


