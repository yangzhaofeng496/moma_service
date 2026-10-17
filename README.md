# moma_service

## 作用

集中定义机器人巡检系统使用的 ROS1 消息和服务接口，不运行独立节点。

## 编译

```bash
catkin_make --pkg moma_service
```

## 主要接口

消息：

- `DetectObj`：检测目标类型、位置、置信度、状态和厚度。
- `ResultCount`：巡检总数、已检数和异常数统计。

服务：

- `DetectPic`：请求图像检测。
- `RobotStart`、`RobotTerminate`、`RobotCompleted`：巡检任务生命周期控制。
- `RobotReportData`：上报单个巡检点的检测结果。
- `RobotHeartbeat`：机器人心跳。
- `EnableRobot`、`DisableRobot`、`ServoJ`、`MoveJoint`、`MovePose`：机械臂控制。
- `CapSavePic`：保存图像。

具体字段以 `msg/` 和 `srv/` 目录中的定义为准。
