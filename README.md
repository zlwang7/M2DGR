


# M2DGR： a Multi-modal and Multi-scenario SLAM Dataset for Ground Robots 
## First Author: [Jie Yin](https://github.com/sjtuyinjie?tab=repositories)
<div align=center>
<img src="https://github.com/sjtuyinjie/mypics/blob/main/bigsix.jpg" width="800px">

</div>
<p align="center">Figure 1. Sample Images</p>


## Updates

### 2022.12.13 Our new work coming soon! Codes and datasets will be available in https://github.com/sjtuyinjie/M2DGR-plus and https://github.com/SJTU-ViSYS/Ground-Fusion upon paper acceptance. 

### 2022.9.13 welcome to follow and star our new work: Ground-Challenge at https://github.com/sjtuyinjie/Ground-Challenge. Feel free to propose issues if needed.

### 2022.06.20   Thanks Jialin Liu (Fudan University) for his work to test LVI-SAM on M2DGR. Following is the link of their modified LVI-SAM version [link](https://github.com/electech6/LVI-SAM_detailed_comments). Refer [Link](https://github.com/SJTU-ViSYS/M2DGR/blob/main/LVISAM-modified.md) for detailed information. And the configuration files for LVI-SAM on M2DGR are given in [launch file](https://github.com/SJTU-ViSYS/M2DGR/blob/main/module_sam.launch),[camera file](https://github.com/SJTU-ViSYS/M2DGR/blob/main/my_params_camera.yaml) and [lidar file](https://github.com/SJTU-ViSYS/M2DGR/blob/main/my_params_lidar.yaml). Feel free to test the demo on your machine!

<center>
<img src="https://github.com/shuttworth/Record_Datasets_For_LVI-SAM/blob/main/img/gate_01_v1.gif" width="70%">
</center>

<center>
<img src="https://github.com/shuttworth/Record_Datasets_For_LVI-SAM/blob/main/img/street_08_v1.gif" width="70%">
</center>

<p align="left">LVI-SAM on M2DGR</p>

2022.02.18   We have upload a brand new SLAM dataset with GNSS, vision and IMU information. Here is our link [SJTU-GVI](https://github.com/sjtuyinjie/SJTU_GVI). Different from M2DGR, new data is captured on a real car and it records GNSS raw measurements with a Ublox ZED-F9P device to facilitate GNSS-SLAM. Give us a star and folk the project if you like it.


2022.02.01   Our work has been accepted by ICRA2022!


## NOTICE
### We strongly recommend that the newly proposed SLAM algorithm be tested on our data, because our data has following features:
1. A  rich pool of sensory information including vision, lidar, IMU, GNSS,event, thermal-infrared images and so on
2. Various scenarios in real-world environments including lifts, streets, rooms, halls and so on.
3. Our dataset brings great challenge to existing SLAM algorithms including LIO-SAM and ORB-SLAM3. If your proposed algorihm outperforms SOTA systems on M2DGR, your paper will be much more convincing and valuable.


## ABSTRACT:

We introduce M2DGR: a novel large-scale dataset collected by a ground robot with a full sensor-suite including six fish-eye and one sky-pointing RGB cameras, an infrared camera, an event camera, a Visual-Inertial Sensor (VI-sensor), an inertial measurement unit (IMU), a LiDAR, a consumer-grade Global Navigation Satellite System (GNSS) receiver and a GNSS-IMU navigation system with real-time kinematic (RTK) signals. All those sensors were well-calibrated and synchronized, and their data were recorded simultaneously. The ground truth trajectories were obtained by the motion capture device, a laser 3D tracker, and an RTK receiver.  The dataset comprises 36 sequences (about 1TB) captured in diverse scenarios including both indoor and outdoor environments. We evaluate state-of-the-art SLAM algorithms on M2DGR. Results show that existing solutions perform poorly in some scenarios. For the benefit of the research community, we make the dataset and tools public.

Keywords:Dataset, Multi-model, Multi-scenario,Ground Robot

## MAIN CONTRIBUTIONS:
* We collected long-term challenging sequences for ground robots both indoors and outdoors with a complete sensor suite, which includes six surround-view fish-eye cameras, a sky-pointing fish-eye camera, a perspective color camera, an event camera, an infrared camera, a 32-beam LIDAR, two GNSS receivers, and two IMUs. To our knowledge, this is the first SLAM dataset focusing on ground robot navigation with such rich sensory information.
* We recorded trajectories in a few challenging scenarios like lifts, complete darkness, which can easily fail existing localization solutions. These situations are commonly faced in ground robot applications, while they are seldom discussed in previous datasets.
* We launched a comprehensive benchmark for ground robot navigation. On this benchmark, we evaluated existing state-of-the-art SLAM algorithms of various designs and analyzed their characteristics and defects individually.


## Video
[![ICRA2022 Presentation](cover.png)](https://www.youtube.com/watch?v=73enWUwxJ1k)



For Chinese users, try [![bilibili](cover.png)](https://www.bilibili.com/video/BV1q3411G7iF/)










## 1.LICENSE
This work is licensed under MIT license. International License and is provided for academic purpose. If you are interested in our project for commercial purposes, please contact us on 1195391308@qq.com for further communication. 

If you face any problem when using this dataset, feel free to propose an issue. And if you find our dataset helpful in your research, simply give this project a 
. 

The paper has been accepted by both [RA-L](https://www.ieee-ras.org/publications/ra-l/) and [ICRA 2022](https://icra2022.org/). A preprint version of the paper in [Arxiv](https://arxiv.org/abs/2112.13659) and [IEEE RA-L](https://ieeexplore.ieee.org/document/9664374).If you use M2DGR in an academic work, please cite:
~~~
@ARTICLE{9664374,
  author={Yin, Jie and Li, Ang and Li, Tao and Yu, Wenxian and Zou, Danping},
  journal={IEEE Robotics and Automation Letters}, 
  title={M2DGR: A Multi-sensor and Multi-scenario SLAM Dataset for Ground Robots}, 
  year={2021},
  volume={},
  number={},
  pages={1-1},
  doi={10.1109/LRA.2021.3138527}}
~~~



## 2.SENSOR SETUP
### 2.1 Acquisition Platform
Physical drawings and schematics of the ground robot is given below. The unit of the figures is centimeter.

<div align=center>
<img src="https://github.com/sjtuyinjie/mypics/blob/main/newcar4.png" width="800px">
</div>

<p align="left">Figure 2. The GAEA Ground Robot Equipped with a Full Sensor Suite.The directions of the sensors are marked in different colors,red for X,green for Y and blue for Z.</p>









### 2.2 Sensor parameters

All the sensors and track devices and their most important parameters are listed as below:

* **LIDAR** Velodyne VLP-32C, 360 Horizontal Field of View (FOV),-30 to +10 vertical FOV,10Hz,Max Range 200 m,Range Resolution 3 cm, Horizontal Angular Resolution 0.2°.  

* **RGB Camera** FLIR Pointgrey CM3-U3-13Y3C-CS,fish-eye lens,1280*1024,190 HFOV,190 V-FOV, 15 Hz  
* **GNSS** Ublox M8T, GPS/BeiDou, 1Hz  
* **Infrared Camera**,PLUG 617,640*512,90.2 H-FOV,70.6 V-FOV,25Hz;  
* **V-I Sensor**,Realsense d435i,RGB/Depth 640*480,69H-FOV,42.5V-FOV,15Hz;IMU 6-axix, 200Hz  
* **Event Camera** Inivation DVXplorer, 640*480,15Hz;  
* **IMU**,Handsfree A9,9-axis,150Hz;  
* **GNSS-IMU** Xsens Mti 680G. GNSS-RTK,localization precision 2cm,100Hz;IMU 9-axis,100 Hz;  
* **Laser Scanner** Leica MS60, localization 1mm+1.5ppm  
* **Motion-capture System** Vicon Vero 2.2, localization accuracy 1mm, 50 Hz;

The rostopics of our rosbag sequences are listed as follows:

* LIDAR: `/velodyne_points` 

* RGB Camera: 
`/camera/left/image_raw/compressed `,  
`/camera/right/image_raw/compressed `,  
`/camera/third/image_raw/compressed `,  
`/camera/fourth/image_raw/compressed `,  
`/camera/fifth/image_raw/compressed `,  
`/camera/sixth/image_raw/compressed `,  
`/camera/head/image_raw/compressed `  
* GNSS Ublox M8T:  
`/ublox/aidalm `,  
`/ublox/aideph `,  
`/ublox/fix `,  
`/ublox/fix_velocity `,  
`/ublox/monhw `,  
`/ublox/navclock `,  
`/ublox/navpvt `,  
`/ublox/navsat `,  
`/ublox/navstatus `,  
`/ublox/rxmraw `  


* Infrared Camera:`/thermal_image_raw ` 
* V-I Sensor:  
`/camera/color/image_raw/compressed `,  
`/camera/imu`
* Event Camera:  
`/dvs/events`,  
`/dvs_rendering/compressed`
* IMU: `/handsfree/imu `
 

## 3.DATASET SEQUENCES


**We make public ALL THE SEQUENCES with their GT now.**

<div align=center>

<img src="https://github.com/sjtuyinjie/mypics/blob/main/dynamic.gif" width="400px">
</div>

<p align="left">Figure 3. A sample video with fish-eye image(both forward-looking and sky-pointing),perspective image,thermal-infrared image,event image and lidar odometry</p>


An overview of M2DGR is given in the table below:
Scenario|Street|Circle|Gate|Walk|Hall|Door|Lift|Room|Roomdark|TOTAL
--|:--|:--:|--:|--:|--:|--:|--:|--:|--:|--:
Number | 10|2|3|1|5|2|4|3|6|36
Size/GB|590.7|50.6| 65.9|21.5| 117.4 |46.0|112.1|45.3|171.1|1220.6
Duration/s |7958 | 478| 782 |291 |1226|588|1224|275|866|13688
Dist/m |7727.72| 618.03| 248.40|263.17|845.15|200.14|266.27|144.13|395.66|10708.67
Ground Truth  |RTK/INS |RTK/INS |RTK/INS |RTK/INS |Leica |Leica |Leica |Mocap|Mocap| ---



### 3.1 Outdoors

<div align=center>
<img src="https://github.com/sjtuyinjie/mypics/blob/main/forgithub/outdoor.png" width="400px">
<p align="center">Figure 4. Outdoor Sequences:all trajectories are mapped in different colors.</p>
  


Sequence Name|Collection Date|Total Size|Duration|Features|Rosbag|GT
--|:--|:--:|--:|--:|--:|--:
gate_01|2021-07-31|16.4g|172s|dark,around gate|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/ET3mU1rvdTpEl8VYvC25q7YB5pmPQlwru0jBbQ9iu0oAMA?e=LrKUpJ)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EfipLVtlRChHvwklkDPylPgBSIQry0_JdfqH-6DaxWCaNA?e=idVsY4)
gate_02|2021-07-31|27.3g|327s|dark,loop back|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EY7fHSh4NnxBvemze1JS8TEBy5beLh_xlJ6mdi2IYmeY9w?e=xIcvDe)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ETaXuADPMrNKlFn6pI9aqeoBmcgHr86fIsvDBB6cSaTBLA?e=gzaHPW)
gate_03|2021-08-04|21.9g|283s|day|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EUthdjvVIVdFmFxR82jzVqUBQTpsfvvb26pYtb0yj-_hlw?e=6MWwmJ)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ETj90pEu4PBDpYIoI0nWEAMBiWU68VXMXpU7MKwWnpdXxA?e=1KLdX3)


Sequence Name|Collection Date|Total Size|Duration|Features|Rosbag|GT
--|:--|:--:|--:|--:|--:|--:
Circle_01|2021-08-03|23.3g|234s|Circle|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EUVwex_LapBFrWV4ZtXocoYBE29aoQkPVdwWGhSFcioEtQ?e=YRRV9L)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EUlLxD27cGFArKGnpwkGrgEBr9FVGaSojLGVhJSNKaLLqQ?e=Bkptlj)
Circle_02|2021-08-07|27.3g|244s|Circle|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EeVG96IFCfxDlDLH8xefa3EBEMjCm4_8__V8JZ4ivMGoww?e=FVgjhB)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EfVe45nxzepBsZSFp-yzqRMBpg_PYdZVS1L3FOYqA8WdcA?e=5BcVrA)

Sequence Name|Collection Date|Total Size|Duration|Features|Rosbag|GT
--|:--|:--:|--:|--:|--:|--:
street_01|2021-08-06|75.8g|1028s|street and buildings,night,zigzag,long-term|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EavjoipiTMRIjUvmodSGGsoB8rg0_pOkp6pqDScr8h4zvQ?e=OjtWkL)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ES2todVoF5VGmLo8WwKxcRYB4nyw6-zNR86I4BxAPnv_wg?e=ZtalWi)
street_02|2021-08-03|83.2g|1227s|day,long-term|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EQj5QBBHONpFj-hlvXOQBr0BM0NP9nhNuw-X9UtwOMMuNw?e=ZrxudN)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EfOmlQh5BvJAorfLiI7orFgBJRR94rEjU163lvWgLAlA2Q?e=Z7mAcd)
street_03|2021-08-06|21.3g|354s|night,back and fourth,full speed|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EQU95R6TOAZIkaoFuHJLU-kB9qJEIDeEsECB3Gjc9Nmx8A?e=J1AKwY)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EQ4l4FNo69dPjWco2Pk8Zy4BuPWTFUGQHOv2KdO4MbTv2g?e=ZZf9ok)
street_04|2021-08-03|48.7g|858s|night,around lawn,loop back|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/Ea72BxSXFYhDrp_FGNlJ2ukBx3CQSlv0Wah5nFUJtIntrw?e=4rwi7H)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EadWM6nH74hBusYGre63WRcB0fM_ynkFJu2ibpSWtr5P-w?e=K7FJzV)
street_05|2021-08-04|27.4g|469s|night,staight line|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EUClV6vL2zhAicOwwO1WiroBK-fPzTu8K8NtMfgdMAxIqw?e=r50mNo)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EYrYgnp716xKo0-wcyVX2Z4BTnbbZuQrwYgaJIzREs923Q?e=gcGt7I)
street_06|2021-08-04|35.0g|494s|night,one turn|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EZ4HAXvNQXRCgRKSLpE3yX0BsM24PkXwAd-NopVc7ueNzA?e=oUw91h)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ETFW7vEEmp9JvJiVZef0wooBN9r7mt8jj1WmVdzzNiIp7A?e=67FHW4)
street_07|2021-08-06|77.2g|929s|dawn,zigzag,sharp turns|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EfScTXrKjAdGg1w9xZ-yZgIBWu9gIswakQToN9guMPatQQ?e=YvjAUg)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EefcYHlgA-RJiTl1jZl9r4ABr2YcrmTX7InDG_W6cHHrFQ?e=NQB203)
street_08|2021-08-06|31.2g|491s|night,loop back,zigzag|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EdgojePkM2ZNszS6JM80D90B-2q68wWQ1vZijzeaH-IQrw?e=iwVIiX)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/Ecv4IRMW5rBPn22pxW-xEYQBGinyVxrP6htbpS3HGnOpiA?e=TJXzJz)
street_09|2021-08-07|83.2g|907s|day,zigzag|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/Ee5hiGAdou5OvPI_xeOHBh4BtRntB8-5qLXqCuXhXNB-Yw?e=wEkptw)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EXb__m3Z0wdLkv_ybnXDOlUBVV41XM8_G1yHNO9oZKJE1w?e=xaZBGo)
street_010|2021-08-07|86.2g|910s|day,zigzag|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EfcpNeq8p-NLp7kCkaz0WugBf1c9TGtDbVBDy2QHF5rPvQ?e=lpnnAJ)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ETWkYfjfaP5PuMUJmbHsLS0Btby-9W7V9n4bfob9DGP-pw?e=iOGOBW)
walk_01|2021-08-04|21.5g|291s|day,back and fourth|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EZn2REI4E2BLurJXTaTDpYcBIMOoO3CKh9dsPbcMeMYTKg?e=R4cSKy)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EfNamQlwIeRGl0-gjktD1UEBMpXSWScVLL7VL1WUPiInhw?e=zmbJNp)
</div>


### 3.2 Indoors
<div align=center>

<img src="https://github.com/sjtuyinjie/mypics/blob/main/forgithub/lift.jpg" width="400px">

<p align="left">Figure 5. Lift Sequences:The robot hang around a hall on the first floor and then went to the second floor by lift.A laser scanner track the trajectory outside the lift</p>
  

  

Sequence Name|Collection Date|Total Size|Duration|Features|Rosbag|GT
--|:--|:--:|--:|--:|--:|--:
lift_01|2021-08-04|18.4g|225s|lift|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EZp-yCPxrxNBg5cM_aWualABVCNktGm29u0RA2UGVmyp2Q?e=BChvEN)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EQkO6B_IDPtItavRTjwedkoBQDUc6vV2jqtkOsmnWL7lhw?e=dDNVaE)
lift_02|2021-08-04|43.6g|488s|lift|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EfXP5V6Yi3tEvQL-Gbaq4QcBEVNxqacC-tltlzYnFnW7zQ?e=vgyEzS)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EX9iTyrQjWpKu9dI0Vx9uUkBAeLjUuU-PwUVT4yl1Tit1Q?e=toxiWg)
lift_03|2021-08-15|22.3g|252s|lift|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EWWG7OgCmTpIj_VZixYTkzsBew8ONoMrI13acbZ_8svV3g?e=1OVDYA)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EQgymOgmbiVDt8NPcb-HiYoBUKkfzJZeJnKZdOvAXMgWtA?e=mzM6kq)
lift_04|2021-08-15|27.8g|299s|lift|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/ETrPaBIVaV1EtTVUG9effPIBK1LiJ3pGK93jAdhLZU_Pjg?e=ekVtWl)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EYgfjuI3fZ9AsjGH1jKwwqcBlXsaRaEZ9TS8Y1VHlTpyCw?e=0fMc5n)

  
  
  

Sequence Name|Collection Date|Total Size|Duration|Features|Rosbag|GT
--|:--|:--:|--:|--:|--:|--:
hall_01|2021-08-01|29.1g|351s|randon walk|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EWQ2bcxWRgZLtK_eSIgnNmoB_ozAyXeEU_MmlVqPZeiB7Q?e=BKghlK)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EYxqt8qdK2hCgzW7qoQQWEIBvWgJAC7rotStNWxiEXDigg?e=lJabX7)
hall_02|2021-08-08|15.0g|128s|randon walk|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EaAEMKhvsgJCn0bSvlNOENkB-jVOOH4gxrxATSCbwPdUng?e=xCXoXE)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EWybRtZdpVhBtfPbB4PlvigBNXjgmp8PzHbcMBqUA2ivhA?e=WRoQN9)
hall_03|2021-08-08|20.5g|164s|randon walk|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EWyFq_niW4xIkk9pg2tLVfMBfT9JaC0ZUa0CogD6sND6Ew?e=ODUNxq)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EVL6pWtJ0yVNgDkZLYonkrMBcVAVN8pO2F5Kdh5tSh9fdg?e=nGDMba)
hall_04|2021-08-15|17.7g|181s|randon walk|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EV0oYa2MNi1HqmhvCM1pbboBAqQlij03bPifdyd_cqZUDA?e=P56O61)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EUrqpdjawd9HgF7aVQxYL_cBKIye_pFquj3tobdSnj_H2w?e=iAEG0u)
hall_05|2021-08-15|35.1g|402s|circle|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EQRFrzmO2BxFmeAZV_ifTpsBJjdIM7XjQAnmnuDdhE9-Vg?e=WDZwUt)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EfuK4fEcs0JEtXGNWjEVI9UB9qHZjd7Y4WAs9XLZgmA4hQ?e=zQrXDW)





<img src="https://github.com/sjtuyinjie/mypics/blob/main/forgithub/room.png" width="400px">

<p align="center">Figure 6. Room Sequences:under a Motion-capture system with twelve cameras.</p>
  
Sequence Name|Collection Date|Total Size|Duration|Features|Rosbag|GT
--|:--|:--:|--:|--:|--:|--:
room_01|2021-07-30|14.0g|72s|room,bright|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EfG372xf9h9Dl0xjm5XcDgoB7JP0SsWJfAfpfO2CU-QOmw?e=XINjaC)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ER6DA9bugPZNphRXA-zT_8QB4Hj0r0564NXknXHrlWuEcg?e=SlLMZM)
room_02|2021-07-30|15.2g|75s|room,bright|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EaVK6tu2gs5NnOpAhhWrTPEBK_cpPGiq_1vDXET2GTCeNQ?e=2QpXCE)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ES-9QFWKEeBNqxyMv5dJe7EB5YxfTzi8v3x2Hf1aLObnAg?e=ifwPHL)
room_03|2021-07-30|26.1g|128s|room,bright|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EZfZZNphLARHl0H4zLbM_kABbwkgl5efzhVqUeia8T-adQ?e=aWHDbk)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EbcfH0djHMxCos8kfIH4i6wBBazfAOcFu6DLDSThzATf-w?e=W630hf)
room_dark_01|2021-07-30|20.2g|111s|room,dark|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EXx8PoEtySBCvzFbYnQrFIkBDnjodZJ97_EVvXeSHW3snw?e=ZVsp9L)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/Ee4o6_FIKeNPqG-f2ahm7p0BPUExaiMABzHfvhj1xGRitQ?e=6IwX76)
room_dark_02|2021-07-30|30.3g|165s|room,dark|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/ERbnfghuh-NFo9W0Sev8cggBQQiTQLzjFiQy5So7j3J9tw?e=KEbKXr)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/Ef_CAOf_e-VLlu9xdAm2QSIBTP0B1QNm7uRG-s9EWib4hg?e=95qPDA)
room_dark_03|2021-07-30|22.7g|116s|room,dark|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EXwiG7vYnsdKh2OotVeQKYsByEtckw39FPXiWLXBrA5kqw?e=0ZR9jg)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EXjFPcy4SrlCk5ZRvY9nGMkBzZuaSC6NVqPweU-1_OozuQ?e=E9uKVh)
room_dark_04|2021-08-15|29.3g|143s|room,dark|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EQqOn3hvPFVHin6apSr233wBJuG69N2iDPSauYQhKker4A?e=QUABfA)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EZ01sVBMNV9FloNLhb7XdeIB1bIp0GtwoxS0pXirZ9dO6A?e=KFFArd)
room_dark_05|2021-08-15|33.0g|159s|room,dark|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/Ead7Ayxgh0REuN1J5SPDFFUBKMF8X3w2eGBCjOgefOs-VA?e=czasTj)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ET5ihyrgN3FCpR_i6yZeVPYBBANJ57Cq5ly44ddTOpPl7Q?e=la7ifj)
room_dark_06|2021-08-15|35.6g|172s|room,dark|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EUefMvN3g6hMos_qxocEH-4BYMFnt-yF4HxECfx3nDy81Q?e=laORp2)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/ESjB6YrPnKhMuSb-hM_ZSw0BltnaLhn41H6LgexZjebNsA?e=xuEjTp)
</div>




  

  
### 3.3 alternative indoors and outdoors
  
<div align=center>
<img src="https://github.com/sjtuyinjie/mypics/blob/main/forgithub/door.jpg" width="400px">
<p align="center">Figure 7. Door Sequences:A laser scanner track the robot through a door from indoors to outdoors.</p>


Sequence Name|Collection Date|Total Size|Duration|Features|Rosbag|GT
--|:--|:--:|--:|--:|--:|--:
door_01|2021-08-04|35.5g|461s|outdoor to indoor to outdoor,long-term|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/ERxIk8o_HwlAgbqJ2wwgHl8Br3uBZhyuBbxM2bG_0A6QYA?e=uQr94R)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EVgYKmnhIy9AhCC1tOOKUOYB91dEx3mGmFQ9ewLtlNDw6g?e=uylMro)
door_02|2021-08-04|10.5g|127s|outdoor to indoor,short-term|[Rosbag](https://sjtueducn-my.sharepoint.com/:u:/g/personal/594666_sjtu_edu_cn/EWCKNoEfAmxGsahwnJDYWS4BfgEPoONQKR8HAuZA4ng5eg?e=KB9PYF)|[GT](https://sjtueducn-my.sharepoint.com/:t:/g/personal/594666_sjtu_edu_cn/EdOFufA_mTxCoVlzcu285xoBpNQkaTaYdfL8Nd0Nad6mBQ?e=bxEbOK)

</div>


## 4. CONFIGURERATION FILES
For convenience of evaluation, we provide configuration files of some well-known SLAM systems as below:

[A-LOAM](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/aloam/aloam_velodyne_HDL_32.launch),

[LeGO-LOAM](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/legoloam/run.launch),

[LINS](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/lins/exp_port.yaml),

[LIO-SAM](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/liosam/params.yaml),

[VINS-MONO](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/vins/mytest.launch),

[ORB-Pinhole](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/orb3/paperd435i.yaml),

[ORB-Fisheye](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/orb3/paperleft.yaml),

[ORB-Thermal](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/orb3/paperthermal.yaml),

[CUBMAPSLAM](https://github.com/sjtuyinjie/toolkit/blob/main/config_files/cubemapslam/runCubemapstreet_06.sh)

## 5.DEVELOPMENT TOOLKITS
### 5.1 Extracting Images
* For rosbag users, first make image view
~~~
roscd image_view
rosmake image_view
sudo apt-get install mjpegtools
~~~

open a terminal,type roscore.And then open another,type
~~~
rosrun image_transport republish compressed in:=/camera/color/image_raw raw out:=/camera/color/image_raw respawn="true"
~~~
* For non-rosbag users,just take advantage of following script  [export_tum](https://github.com/sjtuyinjie/toolkit/blob/main/export_tum.py),[export_euroc](https://github.com/sjtuyinjie/toolkit/blob/main/export_euroc.py) and [get_csv](https://github.com/sjtuyinjie/toolkit/blob/main/img2csv.py) to get data in formats of Tum or EuRoC.

### 5.2 Evaluation
We use open-source tool [evo](https://github.com/MichaelGrupp/evo) for evalutation.
To install evo,type
~~~
pip install evo --upgrade --no-binary evo
~~~
To evaluate monocular visual SLAM,type
~~~
evo_ape tum street_07.txt your_result.txt -vaps
~~~
To evaluate LIDAR SLAM,type
~~~
evo_ape tum street_07.txt your_result.txt -vap
~~~
To test GNSS based methods,type
~~~
evo_ape tum street_07.txt your_result.txt -vp
~~~

### 5.3 Calibration
For camera intrinsics,visit [Ocamcalib](http://sites.google.com/site/scarabotix/ocamcalib-toolbox) for omnidirectional model.
visit [Vins-Fusion](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion) for pinhole and MEI model.
use [Opencv](https://opencv.org/) for Kannala Brandt model

For IMU intrinsics,visit [Imu_utils](https://github.com/gaowenliang/imu_utils)

For extrinsics between cameras and IMU,visit [Kalibr](https://github.com/ethz-asl/kalibr)
For extrinsics between Lidar and IMU,visit [Lidar_IMU_Calib](https://github.com/APRIL-ZJU/lidar_IMU_calib) 
For extrinsics between cameras and Lidar, visit [Autoware](https://github.com/Autoware-AI/autoware.ai) 
### 5.4 Getting RINEX files
For GNSS based methods like [RTKLIB](http://www.rtklib.com/),we usually need to get data in the format of RINEX. To make use of GNSS raw measurements, we use [Link](https://github.com/TakahashiJinxu/ublox2rinex) toolkit.

### 5.5 ROS drivers for UVC cameras 
We write a ROS driver for UVC cameras to record our thermal-infrared image. 
[UVC ROS driver](https://github.com/sjtuyinjie/toolkit/tree/main/thermal_ws/src)


## 6.FUTURE PLANS
In the future, we plan to update and extend our project from time to time, striving to build a comprehensive SLAM benchmark similar to the KITTI dataset for ground robots.
### If you have any suggestions or questions, do not hesitate to propose an issue. And if you find our dataset helpful in your research, a simple star is the best affirmation for us.

## 7.ACKNOWLEGEMENT
This work is supported by NSFC(62073214). Authors from SJTU hereby express our appreciation.

