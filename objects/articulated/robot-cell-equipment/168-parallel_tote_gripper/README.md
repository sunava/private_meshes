# Parallel Gripper with Tote Fingers

Electric two-finger parallel gripper with long flat fingers and rubber pads that pinch a tote's rail from above; each finger closes 41.5 mm.

Original concept model by Vanessa Hassouna, developed for AICOR Solutions.
Typology drawn from a public product reference; not a replica of, or affiliated with, any manufacturer's product.

`model.blend` is editable in Blender 4.0 or newer. Its timeline shows closed/rest at frame 1,
an inspection pose at frame 60, and closed/rest again at frame 120.
`model.urdf` loads independently using only local `assets/*.glb` files.
Licensed under BSD-3-Clause (see LICENSE.txt and NOTICE.md); keep both with every copy.

Coordinates are metres, Z up, front toward negative Y. Origin at the centre of the flange face, the bottom of the model as it stands here: the tool axis is +Z, the fingers point up and close along X (open at rest).
Use a unique URDF parser prefix for each instance.
Collision uses one box for the housing and one each for every finger plate and pad.
Masses/inertias are approximate model parameters (about 0.9 kg in all), not manufacturer specifications.

## Moving parts

| Joint | Motion | Inspection position |
| --- | --- | --- |
| `parallel_tote_gripper_right_finger_joint` | prismatic | 0.03 |
| `parallel_tote_gripper_left_finger_joint` | prismatic | 0.03 |

## Interaction frames

| Frame | Attached to | Purpose |
| --- | --- | --- |
| `parallel_tote_gripper_flange_mount` | `parallel_tote_gripper_body` | tool_attachment |
| `parallel_tote_gripper_pad_centre` | `parallel_tote_gripper_body` | grasp |

The URDF supplies geometry, articulation and frames. It does not model the drive, grip-force control, finger synchronisation (the two joints are independent), object detection or the tool flange's bolt pattern.
