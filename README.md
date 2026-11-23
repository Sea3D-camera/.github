# 🌊 Sea3D – Bachelor Thesis Code Overview

**Sea3D: An Underwater 3D Reconstruction Camera**
Stereo matching and depth estimation on an NVIDIA Jetson Orin AGX for underwater 3D reconstruction.

This organization holds all the code repositories from my bachelor thesis by [@HJGrant](https://github.com/HJGrant).

📄 **Full thesis text:** [Sea3D – An Underwater 3D Reconstruction Camera (PDF)](https://github.com/Sea3D-camera/Sea3D/blob/main/thesis_reader/Sea3D__An_Underwater_3D_Reconstruction_Camera.pdf)

> [!TIP]
> **Start with [`Sea3D`](https://github.com/Sea3D-camera/Sea3D).** It's the main repo, with the final depth map and point cloud pipeline.

---

## ⭐ Main System

| Repo | Description |
|---|---|
| [**Sea3D**](https://github.com/Sea3D-camera/Sea3D) | 🎯 Main thesis repo. Stereo rectification, depth maps (OpenCV + VPI), triangulation and underwater point clouds on the Jetson Orin AGX, plus calibration files and the full thesis PDF. |
| [Sea3D_field_test](https://github.com/Sea3D-camera/Sea3D_field_test) | 🚤 Field test code. CSI 4K camera stream over the BlueROV2 tether, parallel stereo recording on the Orin and the Blue Robotics Pinger (pre-ROS). |

## 📷 Stereo Depth Estimation

| Repo | Description |
|---|---|
| [opencv_test](https://github.com/Sea3D-camera/opencv_test) | Stereo FRAMOS IMX585 setup. Calibrated stereo rectification, underwater rectification and depth maps, GStreamer helpers. The earlier development version of the Sea3D pipeline. |
| [bi3d_vpi](https://github.com/Sea3D-camera/bi3d_vpi) | 🧠 Bi3D learned stereo depth integrated on the Jetson Orin with GStreamer for live depth. |
| [Bi3D](https://github.com/Sea3D-camera/Bi3D) | 🍴 Fork of NVIDIA's [Bi3D](https://github.com/NVlabs/Bi3D) (CVPR 2020), modified to run on the Orin. |

## 🔵 Dome Port Calibration & Image Quality

| Repo | Description |
|---|---|
| [mono_dome_port_calibration](https://github.com/Sea3D-camera/mono_dome_port_calibration) | In-air monocular calibration and pose estimation sketches for a camera behind a dome port. |
| [dome_port_quality_eval](https://github.com/Sea3D-camera/dome_port_quality_eval) | 🔬 Evaluates how a dome port affects image quality (SSIM vs. focus distance and aperture), using Blender image sequences from the POSER underwater photogrammetry simulator. |

## 🖥️ Jetson Orin Setup

| Repo | Description |
|---|---|
| [opencv_conda_build_on_orin](https://github.com/Sea3D-camera/opencv_conda_build_on_orin) | 🛠️ Script to build OpenCV from source with GStreamer support in a conda env on the Jetson Orin, plus a VPI env. |
| [orin_cam_sync](https://github.com/Sea3D-camera/orin_cam_sync) | ⏱️ Startup script that sets the hardware sync mode of the two stereo cameras (`v4l2-ctl`). |

## 🤖 ROS 2 & Sensors

| Repo | Description |
|---|---|
| [ros2_imu_and_stereo](https://github.com/Sea3D-camera/ros2_imu_and_stereo) | ROS 2 workspace from the thesis: Xsens MTi IMU driver + stereo camera publisher. |
| [bue_robotics_pinger_ROS](https://github.com/Sea3D-camera/bue_robotics_pinger_ROS) | 📡 ROS 2 node for the Blue Robotics Ping sonar. Publishes `[distance, confidence]`. |

## 🧰 3D Processing & Utilities

| Repo | Description |
|---|---|
| [voxel_grid_from_point_cloud](https://github.com/Sea3D-camera/voxel_grid_from_point_cloud) | 🧊 Converts `.ply` point clouds into voxel grids with Open3D. |
| [oak-d_tests](https://github.com/Sea3D-camera/oak-d_tests) | Experiments with the Luxonis OAK-D: dense SLAM, RGB-depth alignment, point clouds and IMU pose estimation. |
| [play_frames](https://github.com/Sea3D-camera/play_frames) | 🎞️ Small pygame tool to play back recorded image sequences as video. |

---

## 🗓️ Timeline

| When | What |
|---|---|
| May 2024 | Stereo rectification & depth maps (`opencv_test`), Bi3D on the Orin |
| Jun 2024 | Field test with the BlueROV2 (`Sea3D_field_test`) |
| Jul 2024 | Dome port calibration, OpenCV build on the Orin, camera sync, pinger ROS node |
| Aug–Sep 2024 | Underwater depth maps & point clouds (`Sea3D`), voxel grids |
| Dec 2024 – Mar 2025 | Dome port quality evaluation, OAK-D experiments, ROS 2 packages |
| Oct 2025 | Thesis PDF added to `Sea3D` |
