<!-- QueryToSerialize:  

TABLE
	status AS "Status",
	expected_hours AS "Expected", 
	actual_hours AS "Actual"
FROM "01-Tasks"
WHERE status = "#task/active"
SORT expected_hours DESC

-->
<!-- SerializedQuery: TABLE status AS "Status", expected_hours AS "Expected", actual_hours AS "Actual" FROM "01-Tasks" WHERE status = "#task/active" SORT expected_hours DESC -->

| File                                                                                                                             | Status       | Expected | Actual |
| -------------------------------------------------------------------------------------------------------------------------------- | ------------ | -------- | ------ |
| [[Wayland support for Java Geometry Expert on flatpack.md]] | #task/active | 16       | 0      |

<!-- SerializedQuery END -->


