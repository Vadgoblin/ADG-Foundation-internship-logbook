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
| [Nix package for Java Geometry Expert](01-Tasks/Nix%20package%20for%20Java%20Geometry%20Expert.md)                                     | 32       | 35.7   |
| [Wayland support for Java Geometry Expert on flatpack](01-Tasks/Wayland%20support%20for%20Java%20Geometry%20Expert%20on%20flatpack.md) | 16       | 18.8   |
| [GCLC flathub](01-Tasks/GCLC%20flathub.md)                                                                                             | 8        | 32.7   |
| [Wayland support for Geogebra discovery on flatpack](01-Tasks/Wayland%20support%20for%20Geogebra%20discovery%20on%20flatpack.md)       | 8        | 13.7   |

<!-- SerializedQuery END -->


