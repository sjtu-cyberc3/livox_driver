# Livox ROS Driver changed by CyberC3

mid70mapping version ：基于 v2.6.0修改

## 修改项

### 20230922 version1.2.0

1. 多激光雷达数据合并发送特性，增加需满足接收到所有激光雷达数据条件 **(会导致输出频率降低，实测10hz -> 9.3hz)**
2. 增加 [/lidar_status]话题，用于发布激光雷达状态信息
3. 增加激光雷达异常状态提示到终端：超过1s，未接收到配置数量激光雷达数据 

### Previous

1. 多激光雷达数据合并发送， 话题名字: [/driver/livox/point_cloud]
2. point.intensity = (float)point_xyzrtl->reflectivity + (float)handle * 0.001; 从反射率可以解析出激光雷达id

## How to use it

### 编译和安装

1. 在本文件下使用 catkin_init_workspace 
2. 本文件夹名字修改为 src
3. catkin_make

### 参数调整

1. launch路径下, [livox_lidar.launch] 中lidar_num，根据实际激光雷达数量进行选择
2. config路径下, [livox_lidar_config.json] 中依据激光雷达数量进行完善，注意以下几点：1 enable_connect, 修改为true; 2 extrinsic_parameter_source, 设置为1

## SDK

使用版本，当前目录 Livox-SDK-master.zip，安装即可。