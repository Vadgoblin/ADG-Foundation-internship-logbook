```dataview
TABLE
	status AS "Status",
	expected_hours AS "Expected", 
	actual_hours AS "Actual", 
	(expected_hours - actual_hours) AS "Remaining" 
FROM "01-Tasks"
WHERE status = "#task/active"
SORT expected_hours DESC
```

