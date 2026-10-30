# UV-C Tote Chamber with Sliding Lid

Top-loading UV-C chamber for one robot tote: a quartz shelf with corner guides, lamps below, beside and in the lid, and a lid that slides sideways onto two posts.

Original concept model by Vanessa Hassouna, developed for AICOR Solutions.
Typology drawn from a public product reference; not a replica of, or affiliated with, any manufacturer's product.

`model.blend` is editable in Blender 4.0 or newer. Its timeline shows closed/rest at frame 1,
an inspection pose at frame 60, and closed/rest again at frame 120.
`model.urdf` loads independently using only local `assets/*.glb` files.
Licensed under BSD-3-Clause (see LICENSE.txt and NOTICE.md); keep both with every copy.

Coordinates are metres, Z up, front toward negative Y. Origin at floor level, centre of the footprint including the lid posts; the lid opens toward positive X, the status display and viewing window face negative Y.
Use a unique URDF parser prefix for each instance.
Collision uses boxes for the plinth, the four chamber walls, the shelf, the corner guides, the lid posts and the lid plate and rims, so the chamber stays open with the lid slid back.
Masses/inertias are approximate model parameters (stainless sheet cabinet, lid 9 kg), not manufacturer specifications.

## Moving parts

| Joint | Motion | Inspection position |
| --- | --- | --- |
| `uvc_tote_chamber_lid_joint` | prismatic | 0.50 |

## Interaction frames

| Frame | Attached to | Purpose |
| --- | --- | --- |
| `uvc_tote_chamber_tote_seat` | `uvc_tote_chamber_body` | place_surface |
| `uvc_tote_chamber_chamber_volume` | `uvc_tote_chamber_body` | container_volume |
| `uvc_tote_chamber_lid_grip` | `uvc_tote_chamber_lid` | grasp |
| `uvc_tote_chamber_lid_closed_sensor` | `uvc_tote_chamber_body` | control |
| `uvc_tote_chamber_wall_anchor` | `uvc_tote_chamber_body` | wall_mount |

The URDF supplies geometry, articulation and frames. It does not model UV-C emission or dose, the lamps' run-up and ageing, the lid/door interlock logic, the lid drive or the status display.
