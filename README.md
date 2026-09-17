<!-- QueryToSerialize:  

TABLE WITHOUT ID
	"[" + file.name + "](" + replace(file.path, " ", "%20") + ")" AS "Link",
	expected_hours AS "Expected", 
	actual_hours AS "Actual"
FROM "01-Tasks"
SORT date(start_date) ASC

-->
<!-- SerializedQuery: TABLE WITHOUT ID "[" + file.name + "](" + replace(file.path, " ", "%20") + ")" AS "Link", expected_hours AS "Expected", actual_hours AS "Actual" FROM "01-Tasks" SORT date(start_date) ASC -->

| Link                                                                                                                                   | Expected | Actual |
| -------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------ |
| [Wayland support for Java Geometry Expert on flatpack](01-Tasks/Wayland%20support%20for%20Java%20Geometry%20Expert%20on%20flatpack.md) | 16       | 18.8   |
| [Wayland support for Geogebra discovery on flatpack](01-Tasks/Wayland%20support%20for%20Geogebra%20discovery%20on%20flatpack.md)       | 8        | 13.7   |
| [Nix package for Java Geometry Expert](01-Tasks/Nix%20package%20for%20Java%20Geometry%20Expert.md)                                     | 32       | 35.7   |
| [GCLC flathub](01-Tasks/GCLC%20flathub.md)                                                                                             | 8        | 32.7   |
| [Patches for GCLC upstream](01-Tasks/Patches%20for%20GCLC%20upstream.md)                                                               | 2        | 2      |
| [Refactor Geogebra Prover](01-Tasks/Refactor%20Geogebra%20Prover.md)                                                                   | 16       | 16.5   |
| [flake.nix for Java Geomtery Expert](01-Tasks/flake.nix%20for%20Java%20Geomtery%20Expert.md)                                           | 4        | 3.5    |
| [Java Geometry Expert in cheerpj fix save and load](01-Tasks/Java%20Geometry%20Expert%20in%20cheerpj%20fix%20save%20and%20load.md)     | 42       | 17.8   |
| [Java Geometry Expert fix point is not on circle](01-Tasks/Java%20Geometry%20Expert%20fix%20point%20is%20not%20on%20circle.md)         | 4        | 11.2   |
| [Appimage and windows exe for JGEX release 0.88](01-Tasks/Appimage%20and%20windows%20exe%20for%20JGEX%20release%200.88.md)             | 10       | 19.8   |
| [Fix online help of JGEX](01-Tasks/Fix%20online%20help%20of%20JGEX.md)                                                                 | 4        | 1.8    |

<!-- SerializedQuery END -->


