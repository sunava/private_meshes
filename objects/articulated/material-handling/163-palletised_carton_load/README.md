# Palletised Carton Load

Flat 1200 x 800 block pallet carrying three layers of taped 600 x 400 cartons, as stored in pallet racking.

Original AICOR concept model. Principal author and design direction: Vanessa Hassouna.
Typology drawn from a public product reference; not a replica of, or affiliated with, any manufacturer's product.

`model.blend` is editable in Blender 4.0 or newer. Its timeline shows closed/rest at frame 1,
an inspection pose at frame 60, and closed/rest again at frame 120.
`model.urdf` loads independently using only local `assets/*.glb` files.
Copy this entire folder, including its notices, for an authorized reuse.

Coordinates are metres, Z up, front toward negative Y. Origin at floor level, centre of the footprint; the 800 mm pallet side faces the front.
Use a unique URDF parser prefix for each instance.
Collision uses one box for the pallet and one for the carton load, so fork pockets are not open.
Masses/inertias are approximate model parameters (pallet plus filled cartons), not specifications.

## Moving parts

The body is a single rigid link; the object has no moving parts, so the rest and inspection renders are the same.

| Joint | Motion | Inspection position |
| --- | --- | --- |
| none | - | - |

## Interaction frames

| Frame | Attached to | Purpose |
| --- | --- | --- |
| `palletised_carton_load_load_top_surface` | `palletised_carton_load_body` | place_surface |
| `palletised_carton_load_stack_anchor` | `palletised_carton_load_body` | wall_mount |
| `palletised_carton_load_front_fork_pocket_grip` | `palletised_carton_load_body` | grasp |
| `palletised_carton_load_back_fork_pocket_grip` | `palletised_carton_load_body` | grasp |

The URDF supplies geometry, articulation and frames. It does not model the fork pockets, stretch wrap, carton crushing or load shifting.
