# Overhead Robot Portal

Free-standing steel portal of two columns and a box-section beam with knee braces, a robot interface plate under the beam centre and a cable tray to one column.

Original concept model by Vanessa Hassouna, developed for AICOR Solutions.
Typology drawn from a public product reference; not a replica of, or affiliated with, any manufacturer's product.

`model.blend` is editable in Blender 4.0 or newer. Its timeline shows closed/rest at frame 1,
an inspection pose at frame 60, and closed/rest again at frame 120.
`model.urdf` loads independently using only local `assets/*.glb` files.
Licensed under BSD-3-Clause (see LICENSE.txt and NOTICE.md); keep both with every copy.

Coordinates are metres, Z up, front toward negative Y. Origin at floor level, centre of the footprint; the beam runs along X, and an inverted robot bolts to the interface plate under the beam centre (robot_mount, 2.2 m above the floor).
Use a unique URDF parser prefix for each instance.
Collision uses one box per column and one for the beam, so the space under the beam stays free.
Masses/inertias are approximate model parameters (steel box sections and plates), not manufacturer specifications.

## Moving parts

The body is a single rigid link; the object has no moving parts, so the rest and inspection renders are the same.

| Joint | Motion | Inspection position |
| --- | --- | --- |
| none | - | - |

## Interaction frames

| Frame | Attached to | Purpose |
| --- | --- | --- |
| `overhead_robot_portal_robot_mount` | `overhead_robot_portal_body` | tool_attachment |
| `overhead_robot_portal_left_floor_anchor` | `overhead_robot_portal_body` | wall_mount |
| `overhead_robot_portal_right_floor_anchor` | `overhead_robot_portal_body` | wall_mount |

The URDF supplies geometry, articulation and frames. It does not model the portal's stiffness or deflection under a moving robot, the floor anchors' strength, the cable dress pack or its safe working load.
