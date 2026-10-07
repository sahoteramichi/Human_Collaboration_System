cmake_minimum_required(VERSION 3.8)
project(workpieces_detection_subsystem)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(collaboration_manipulation_message REQUIRED)

# DetectWorkpieces service
rosidl_generate_interfaces(${PROJECT_NAME}
  "srv/DetectWorkpieces.srv"
  DEPENDENCIES
    collaboration_manipulation_message
)

# Python node
install(
  PROGRAMS
    scripts/WorkpiecesDetectionNode.py
  DESTINATION lib/${PROJECT_NAME}
)

# Configuration files
install(
  DIRECTORY
    config
  DESTINATION share/${PROJECT_NAME}
)

ament_package()
