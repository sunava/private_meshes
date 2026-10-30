# Roller Conveyor with End Stop

Straight roller conveyor at bench height on aluminium-profile legs, with side guides, an end stop and a photo-eye at the pick end and a side-mounted drive box.

Original concept model by Vanessa Hassouna, developed for AICOR Solutions.
Typology drawn from a public product reference; not a replica of, or affiliated with, any manufacturer's product.

`model.blend` is editable in Blender 4.0 or newer. Its timeline shows closed/rest at frame 1,
an inspection pose at frame 60, and closed/rest again at frame 120.
`model.urdf` loads independently using only local `assets/*.glb` files.
Licensed under BSD-3-Clause (see LICENSE.txt and NOTICE.md); keep both with every copy.

Coordinates are metres, Z up, front toward negative Y. Origin at floor level, centre of the footprint; the conveyor runs along Y and the pick end with the end stop faces negative Y.
Use a unique URDF parser prefix for each instance.
Collision uses boxes for the roller bed, the two side guides and the end stop.
Masses/inertias are approximate model parameters (aluminium profile frame and steel rollers), not manufacturer specifications.

## Moving parts

The body is a single rigid link; the object has no moving parts, so the rest and inspection renders are the same.

| Joint | Motion | Inspection position |
| --- | --- | --- |
| none | - | - |

## Interaction frames

| Frame | Attached to | Purpose |
| --- | --- | --- |
| `roller_conveyor_end_stop_pick_surface` | `roller_conveyor_end_stop_body` | place_surface |
| `roller_conveyor_end_stop_transfer_end_surface` | `roller_conveyor_end_stop_body` | place_surface |
| `roller_conveyor_end_stop_floor_anchor` | `roller_conveyor_end_stop_body` | wall_mount |

The URDF supplies geometry, articulation and frames. It does not model the rollers turning (they are part of the body), the drive, accumulation, the photo-eye or any conveying of the load.
