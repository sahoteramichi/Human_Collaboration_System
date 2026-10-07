cmake_minimum_required(VERSION 3.8)
project(management_system)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(collaboration_manipulation_message REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "srv/NotifyPauseCompletion.srv"
  "srv/NotifyTaskCompletion.srv"
  "srv/NotifyTaskResult.srv"
  DEPENDENCIES
    collaboration_manipulation_message
)

install(
  PROGRAMS
    scripts/ManagementSystemNode.py
    ../collaboration_manipulation_module/scripts/EnumerateModule.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
