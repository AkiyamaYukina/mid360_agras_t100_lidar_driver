# Sources / 来源记录

## Third-party code / 第三方代码

| Path | Upstream | Commit | License | Changes |
|---|---|---|---|---|
| `ros2_ws/src/FAST_LIO/` | [hku-mars/FAST_LIO](https://github.com/hku-mars/FAST_LIO), branch `ROS2` | `cc3c9e8b1469b33b8072764d6db2348ed6dc597f` (2026-10-25) | GPL-2.0 | Source unmodified. Left out to save space: the demo GIFs, large pictures and paper PDFs in `doc/`, and the placeholder `PCD/1`. Added: an empty `PCD/.gitkeep`. Some pictures in its README therefore do not load. |
| `ros2_ws/src/FAST_LIO/include/ikd-Tree/` | [hku-mars/ikd-Tree](https://github.com/hku-mars/ikd-Tree) | `e2e3f4e9d3b95a9e66b1ba83dc98d4a05ed8a3c4` (2022-02-08) | GPL-2.0 | Unmodified. A submodule upstream, plain files here, so no `git submodule` step is needed. |
| `ros2_ws/src/livox_ros_driver2/msg/`, `LICENSE.txt` | [Livox-SDK/livox_ros_driver2](https://github.com/Livox-SDK/livox_ros_driver2) | identical to `21445540f0d100dc86a7e6df312dd70bbdb4afdf` (2026-09-21) | MIT | Message definitions unmodified. `CMakeLists.txt` and `package.xml` in that directory are written for this repository and build the messages only. The package keeps Livox's name because FAST-LIO includes `livox_ros_driver2/msg/custom_msg.hpp`. |

Checked on 2026-11-24 by comparing git blob hashes: every FAST_LIO and ikd-Tree file in this repository (apart from the added `PCD/.gitkeep`) has the same hash as upstream at the commits above.

上表的第三方文件在 2026-11-24 用 git blob 哈希逐个和上游比对过：FAST_LIO 和 ikd-Tree 的文件（除新增的空文件 `PCD/.gitkeep`）与上游对应提交完全一致。

## Protocol and measurements / 协议和实测

- The packet formats, frames and parameters in [protocol.en.md](protocol.en.md) / [protocol.zh-CN.md](protocol.zh-CN.md) describe what `linux/mid360_agras.cpp` and `tools/mid360_fov.py` do, plus measurements on real LiDARs between 2026-11-05 and 2026-11-22.
- Cross-check on 2026-11-24: `encode()` in `tools/mid360_fov.py` reproduces five request frames published in [sdcnm/T100-LiDAR](https://github.com/sdcnm/T100-LiDAR) byte for byte (`32/12` ×2, `32/14`, `32/50`, `32/51`).
- Type-C pinout: measured on the LiDAR. The assignment of A4 (PPS) and A8 (GPS message) was added on 2026-11-22; A8 has not been verified to work.

- 协议文档写的是 `linux/mid360_agras.cpp` 和 `tools/mid360_fov.py` 的实际行为，加上 2026-11-05 到 2026-11-22 的实机测量。
- 2026-11-24 交叉核对：`tools/mid360_fov.py` 的 `encode()` 能逐字节复现 [sdcnm/T100-LiDAR](https://github.com/sdcnm/T100-LiDAR) 公开的 5 条请求报文（`32/12` 两条、`32/14`、`32/50`、`32/51`）。
- Type-C 引脚为实测；A4（PPS）和 A8（GPS 报文）的定义在 2026-11-22 加入，A8 没有验证过能用。

## Document layout / 文档结构

The arrangement of the documents (bilingual home pages, a protocol reference in `docs/`, this source record) follows [sdcnm/T100-LiDAR](https://github.com/sdcnm/T100-LiDAR). No text or code was taken from it; that repository is published under its own non-commercial license, this one under GPL-2.0.

文档的组织方式（中英文首页、`docs/` 下的协议说明和本文件）参考了 [sdcnm/T100-LiDAR](https://github.com/sdcnm/T100-LiDAR)，没有使用它的文字和代码。它采用自己的非商业许可，本仓库采用 GPL-2.0。
