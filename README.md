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

| Link | Status | Expected | Actual |
| ---- | ------ | -------- | ------ |

<!-- SerializedQuery END -->


