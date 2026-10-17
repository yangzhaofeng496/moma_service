cmake_minimum_required(VERSION 3.0.2)
project(moma_service)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  moveit_msgs
)

add_message_files(
  FILES
  DetectObj.msg
  ResultCount.msg
)

add_service_files(
  FILES
  MovePose.srv
  MoveJoint.srv
  CapSavePic.srv
  DetectPic.srv
  RobotStart.srv
  RobotReportData.srv
  RobotCompleted.srv
  RobotTerminate.srv
  ServoJ.srv
  EnableRobot.srv
  DisableRobot.srv
)

generate_messages(
  DEPENDENCIES
  moveit_msgs
)

catkin_package(
  CATKIN_DEPENDS
  message_runtime
  moveit_msgs
)
