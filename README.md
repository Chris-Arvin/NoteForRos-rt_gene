# NoteForRos
### python3+anaconda+ros
* rospkg 包含rospy等模块
* python3和tf、tf2_ros不能共存！
---
* catkin-tools 包含catkin_make所需的工具
#### optional
* conda install -c conda-forge ros-rosmsg 包含rosmsg相关内容
* conda install -c conda-forge ros-sensor-msgs 包含sensor相关的msg
//安装好ros相关模块后，可编译一个工作空间看看能否正确执行
---
#### catkin_pkg+python
* rosrun .py文件是不需要修改cmakelist的，只需要按照：https://blog.csdn.net/qq_45779334/article/details/108943681
* 核心：
  * #!/usr/bin/env python：是为了说明python文件为可执行文件，而不是脚本文件。
  * chmod a+x xxx.py：添加文件的可执行权限
---




# 安装rt_gene
For conda users(我使用的是 python3.7)
* conda install pytorch==1.9.0 torchvision==0.10.0 cudatoolkit=11.1 -c pytorch -c conda-forge [替换cuda为显卡对应的版本，先装pytorch，要确认是gpu版本。]
  * pytorch cuda torchvision版本对应查询：https://download.pytorch.org/whl/torch_stable.html
  * 可是尝试用-pytorch -conda-forge -nvidia等 翻墙+强制找官方源
  * 先确认如下三行命令均成功
   ```
   import torch
   import torchvision
   torch.cuda.is_avaiable()
   ```
* conda install -c conda-forge dlib numpy scipy tqdm pillow rospkg opencv empy matplotlib
  * 用conda安装open可能会导致删掉torchvision，如果有问题，更换为pip
  * 用conda安装dlib也可能会导致删掉torchvision。。cao！
  * conda下是opencv，pip下是opencv-python
* 安装cv-bridge
  * 参照：https://note.youdao.com/ynoteshare/index.html?id=9293c9b0dcfe5a87599a0553e3ae9d60&type=note&_time=1638433866667
  * 如果报错找不到catkin_pkg，输入如下命令
   ```
   sudo pip3 install -U catkin_pkg
   ```
* 关于tf和tf2_ros不能在python3上使用的解决办法：
  * 将使用的文件从python2.7中直接粘贴过来。
* 启动方式（自用）
  * 开第一个终端，打开摄像头：
  ```
  roslaunch rt_gene start_webcam.launch
  ```
  * 开第二个终端，先开conda环境，再import cv_bridge，再开landmark检测和gaze估计：
  ```
  conda activate rt_gene
  . Documents/import_cv_bridge.sh
  roslaunch rt_gene estimate_gaze.launch
  ```
