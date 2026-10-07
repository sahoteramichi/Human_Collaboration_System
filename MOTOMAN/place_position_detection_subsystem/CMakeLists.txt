cmake_minimum_required(VERSION 3.8)
project(place_position_detection_subsystem)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(collaboration_manipulation_message REQUIRED)

# DetectPlacePosition service
rosidl_generate_interfaces(${PROJECT_NAME}
  "srv/DetectPlacePosition.srv"
  DEPENDENCIES
    collaboration_manipulation_message
)

# Python node
install(
  PROGRAMS
    scripts/PlacePositionDetectionNode.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
