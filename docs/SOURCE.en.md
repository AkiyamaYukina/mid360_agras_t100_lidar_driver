# Sources

[简体中文](SOURCE.md) · [Back to the home page](../README.en.md)

## Third-party code

| Path | Upstream | Commit | License | Changes |
|---|---|---|---|---|
| `ros2_ws/src/FAST_LIO/` | [hku-mars/FAST_LIO](https://github.com/hku-mars/FAST_LIO), branch `ROS2` | `cc3c9e8b1469b33b8072764d6db2348ed6dc597f` (2026-10-25) | GPL-2.0 | Source unmodified. Left out to save space: the demo GIFs, large pictures and paper PDFs in `doc/`, and the placeholder `PCD/1`. Added: an empty `PCD/.gitkeep`. Some pictures in its README therefore do not load. |
| `ros2_ws/src/FAST_LIO/include/ikd-Tree/` | [hku-mars/ikd-Tree](https://github.com/hku-mars/ikd-Tree) | `e2e3f4e9d3b95a9e66b1ba83dc98d4a05ed8a3c4` (2022-02-08) | GPL-2.0 | Unmodified. A submodule upstream, plain files here, so no `git submodule` step is needed. |
| `ros2_ws/src/livox_ros_driver2/msg/`, `LICENSE.txt` | [Livox-SDK/livox_ros_driver2](https://github.com/Livox-SDK/livox_ros_driver2) | identical to `21445540f0d100dc86a7e6df312dd70bbdb4afdf` (2026-09-21) | MIT | Message definitions unmodified. `CMakeLists.txt` and `package.xml` in that directory are written for this repository and build the messages only. The package keeps Livox's name because FAST-LIO includes `livox_ros_driver2/msg/custom_msg.hpp`. |

Checked on 2026-11-24 by comparing git blob hashes: every FAST_LIO and ikd-Tree file in this repository (apart from the added `PCD/.gitkeep`) has the same hash as upstream at the commits above.
