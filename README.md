# WildBox
WildBox is a **6-species 3D wildlife detection benchmark** built from drone footage. Every frame carries:

- a **2D bounding box** (tight, derived from a SAM3 instance mask),
- a **3D cuboid** (centre, dimensions, full 3×3 rotation) in the camera frame,
- a **track ID** linking the same animal across frames within a segment,
- and per-frame camera intrinsics (focal length + principal point).

The 3D cuboids are recovered from per-segment monocular reconstruction (VGGT) and are normalised within each segment so that the median $|z_{\mathrm{cam}}|$ of valid GT cuboids equals 1; the per-segment scale factor is provided as metadata for users who want absolute-scale evaluation.

Format-wise the dataset is **Omni3D-compatible** (single JSON per split with frame-instance records) and **KITTI-compatible** (per-frame text files with `class trunc occ alpha x1 y1 x2 y2 h w l x y z ry score`).

---

## Headline statistics

| | Train | Val | Total |
|---|---:|---:|---:|
| Videos | 51 | 13 | 64 |
| Segments | 263 | 82 | 345 |
| Frames | 45 979 | 13 779 | 59 758 |
| Annotations (3D cuboids) | 170 554 | 66 951 | 237 505 |
| Native resolution | 1920×1080 | 1920×1080 | — |
| Splits | video-level (no segment leakage) | | |
| Species | giraffe, Grévy's zebra, elephant, plains zebra, rhino, gazelle | | |


## Download

The dataset is shipped as **per-source-group ZIP files** plus a small set of metadata / annotation JSONs at the root.

> **Reviewer link**: `https://<temporary-review-host>/wildbox-v1-reviewer/`
