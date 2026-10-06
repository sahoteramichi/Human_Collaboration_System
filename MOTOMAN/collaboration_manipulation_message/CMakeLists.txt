cmake_minimum_required(VERSION 3.8)
project(collaboration_manipulation_message)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/ErrorInfomation.msg"
  "msg/MonitoringArea.msg"
  "msg/MonitoringAreaList.msg"
  "msg/PersonObstacleDetect.msg"
  "msg/PersonObstacleInfomation.msg"
  "msg/PersonObstaclePoint.msg"
  "msg/PlaceAreaCandidatesList.msg"
  "msg/PlacePositionCandidate.msg"
  "msg/PlacePositionDetectionResult.msg"
  "msg/Property.msg"
  "msg/Status.msg"
  "msg/TargetArea.msg"
  "msg/TaskCommand.msg"
  "msg/TaskCommandList.msg"
  "msg/TaskResult.msg"
  "msg/TaskStatus.msg"
  "msg/EnviromentDetectionInfomation.msg"
  "msg/WorkDetectionResult.msg"
  "msg/WorkDetectionResultList.msg"
  DEPENDENCIES
    geometry_msgs
)

ament_package()
