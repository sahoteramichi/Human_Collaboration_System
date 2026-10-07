cmake_minimum_required(VERSION 3.8)
project(peripheral_environment_detection_subsystem)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(collaboration_manipulation_message REQUIRED)

# Message / service interfaces
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/EnviromentDetectionResult.msg"
  "srv/SetMonitoringArea.srv"
  DEPENDENCIES
    collaboration_manipulation_message
)

# Python node
install(
  PROGRAMS
    scripts/PerEnvDetectNode.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
