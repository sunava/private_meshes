# AMR Top Module, Two Totes

Cabinet for the deck of a mobile robot with two tote pockets under a fixed shroud and a flat cover that slides back to open, plus a light bar and a rear tablet.

Original concept model by Vanessa Hassouna, developed for AICOR Solutions.
Typology drawn from a public product reference; not a replica of, or affiliated with, any manufacturer's product.

`model.blend` is editable in Blender 4.0 or newer. Its timeline shows closed/rest at frame 1,
an inspection pose at frame 60, and closed/rest again at frame 120.
`model.urdf` loads independently using only local `assets/*.glb` files.
Licensed under BSD-3-Clause (see LICENSE.txt and NOTICE.md); keep both with every copy.

Coordinates are metres, Z up, front toward negative Y. Origin at the centre of the module's footprint on its mounting face (the robot deck), which is the bottom of the model; the robot drives toward negative Y, and the cover slides toward positive Y onto rails that overhang the back.
Use a unique URDF parser prefix for each instance.
Collision uses boxes for the cabinet below the pockets, the deck around and between them, the four shroud walls and the cover, so both pockets stay open with the cover slid back.
Masses/inertias are approximate model parameters (sheet cabinet without the robot), not manufacturer specifications.

## Moving parts

| Joint | Motion | Inspection position |
| --- | --- | --- |
| `amr_two_tote_top_module_cover_joint` | prismatic | 0.37 |

## Interaction frames

| Frame | Attached to | Purpose |
| --- | --- | --- |
| `amr_two_tote_top_module_tote_pocket_a` | `amr_two_tote_top_module_body` | place_surface |
| `amr_two_tote_top_module_tote_pocket_b` | `amr_two_tote_top_module_body` | place_surface |
| `amr_two_tote_top_module_cover_grip` | `amr_two_tote_top_module_cover` | grasp |
| `amr_two_tote_top_module_chassis_mount` | `amr_two_tote_top_module_body` | wall_mount |

The URDF supplies geometry, articulation and frames. It does not model the cover drive or lock, the tote presence sensors, the light bar and tablet, or the robot it rides on.
