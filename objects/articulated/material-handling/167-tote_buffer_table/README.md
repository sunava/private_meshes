# Tote Buffer Table, Two Nests

Stainless table with two tote nests side by side, each framed by four L-shaped corner guides and watched by a presence sensor.

Original concept model by Vanessa Hassouna, developed for AICOR Solutions.
Typology drawn from a public product reference; not a replica of, or affiliated with, any manufacturer's product.

`model.blend` is editable in Blender 4.0 or newer. Its timeline shows closed/rest at frame 1,
an inspection pose at frame 60, and closed/rest again at frame 120.
`model.urdf` loads independently using only local `assets/*.glb` files.
Licensed under BSD-3-Clause (see LICENSE.txt and NOTICE.md); keep both with every copy.

Coordinates are metres, Z up, front toward negative Y. Origin at floor level, centre of the footprint; the two nests sit side by side along X.
Use a unique URDF parser prefix for each instance.
Collision uses boxes for the top, the four legs, the lower shelf and every corner-guide leg, so each nest stays open from above and the shelf stays reachable.
Masses/inertias are approximate model parameters (stainless top, legs and shelf), not manufacturer specifications.

## Moving parts

The body is a single rigid link; the object has no moving parts, so the rest and inspection renders are the same.

| Joint | Motion | Inspection position |
| --- | --- | --- |
| none | - | - |

## Interaction frames

| Frame | Attached to | Purpose |
| --- | --- | --- |
| `tote_buffer_table_left_nest_seat` | `tote_buffer_table_body` | place_surface |
| `tote_buffer_table_right_nest_seat` | `tote_buffer_table_body` | place_surface |
| `tote_buffer_table_shelf_surface` | `tote_buffer_table_body` | place_surface |
| `tote_buffer_table_wall_anchor` | `tote_buffer_table_body` | wall_mount |

The URDF supplies geometry, articulation and frames. It does not model the presence sensors, tote locking or the table's load rating.
