本项目仅做代码阅读功能，原项目可参阅本项目fork的源代码地址。本项目内容化繁为简，仅保留和分析核心代码。

原项目地址：https://github.com/3DAgentWorld/S3PO-GS

<p align="center">
  <h1 align="center"> Outdoor Monocular SLAM with Global Scale-Consistent 3D Gaussian Pointmaps
  </h1>
  <p align="center">
     <a ><strong>Chong Cheng*</strong></a>
    ·
    <a ><strong>Sicheng Yu*</strong></a>
    ·
    <a ><strong>Zijian Wang</strong></a>
    ·
    <a ><strong>Yifan Zhou</strong></a>
    ·
    <a href="https://wanghao.tech//"><strong>Hao Wang✉</strong></a>
  </p>
  <p align="center">The Hong Kong University of Science and Technology (GuangZhou)</p>
  <p align="center">(* Equal Contribution)</p>

  <h3 align="center"> ICCV 2025</h3>

[[Project page](https://3dagentworld.github.io/S3PO-GS/)],[[arxiv](https://arxiv.org/abs/2507.03737)]  

⭐Please also check out our previous work [[ICRA 25] OpenGS-SLAM](https://3dagentworld.github.io/opengs-slam/), on which S3PO-GS is a further extension.

# Getting Started

1. Clone S3PO-GS.

```bash
git clone https://github.com/cqy1218/S3PO-GS.git --recursive
cd S3PO-GS
```
## Downloading Datasets

#### Waymo

Save data under the `datasets/waymo` directory.

#### KITTI

KITTI Sequence List (used in this work)

00: 480 - 680

02: 1490 - 1690

03: 280 - 480

05: 0 - 200

06: 160 - 360

07: 0 - 200

08: 2128 - 2328

10: 89 - 289


#### DL3DV


## Run

```bash
## Waymo-405841
CUDA_VISIBLE_DEVICES=0 python slam.py --config "configs/mono/waymo/405841.yaml"

## KITTI-07
CUDA_VISIBLE_DEVICES=0 python slam.py --config "configs/mono/KITTI/07.yaml"

## DL3DV-2
CUDA_VISIBLE_DEVICES=0 python slam.py --config "configs/mono/dl3dv/2.yaml"
```

## Demo

- If you want to view the real-time interactive SLAM window, please change `Results-use_gui` in `base_config.yaml` to True.

- When running on an Ubuntu system, a GUI window will pop up.

## Run on other dataset

- Please organize your data format and modify the code in `utils/dataset.py`.

- Ground truth depth input interface is still retained in the code, although we didn't use it for SLAM.
