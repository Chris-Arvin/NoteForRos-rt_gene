# NoteForRos
### python3+anaconda+ros
* rospkg 包含rospy等模块
---
* catkin-tools 包含catkin_make所需的工具
#### optimal
* conda install -c conda-forge ros-rosmsg 包含rosmsg相关内容
* conda install -c conda-forge ros-sensor-msgs 包含sensor相关的msg
//安装好ros相关模块后，可编译一个工作空间看看能否正确执行
---



# 安装rt_gene
For conda users:
* 用python3.8
* conda install -c pytorch pytorch torchvision cudatoolkit=11.0 -c pytorch [替换cuda为显卡对应的版本，先装pytorch，要确认是gpu版本。]
  * pytorch cuda torchvision版本对应查询：https://download.pytorch.org/whl/torch_stable.html
  * 可是尝试用-pytorch -conda-forge -nvidia等 翻墙+强制找官方源
  * 先确认如下三行命令均成功
   ```
   import torch
   import torchvision
   torch.cuda.is_avaiable()
   ```
* conda install -c conda-forge dlib numpy scipy tqdm pillow rospkg opencv empy matplotlib
//
