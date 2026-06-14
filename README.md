<!-- QueryToSerialize:  

TABLE WITHOUT ID
"[" + file.name + "](" + replace(file.path, " ", "%20") + ")" AS "Link",
	status AS "Status",
	expected_hours AS "Expected", 
	actual_hours AS "Actual"
FROM "01-Tasks"
WHERE status = "#task/active"
SORT expected_hours DESC

-->
<!-- SerializedQuery: TABLE WITHOUT ID "[" + file.name + "](" + replace(file.path, " ", "%20") + ")" AS "Link", status AS "Status", expected_hours AS "Expected", actual_hours AS "Actual" FROM "01-Tasks" WHERE status = "#task/active" SORT expected_hours DESC -->

| Link                                                                                                                                   | Status       | Expected | Actual |
| -------------------------------------------------------------------------------------------------------------------------------------- | ------------ | -------- | ------ |
| [Wayland support for Java Geometry Expert on flatpack](01-Tasks/Wayland%20support%20for%20Java%20Geometry%20Expert%20on%20flatpack.md) | #task/active | 16       | 18.8   |

<!-- SerializedQuery END -->


