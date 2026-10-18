cmake_minimum_required(VERSION 3.20)
project(px4_msgs)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

file(GLOB PX4_MSG_FILES CONFIGURE_DEPENDS
    RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}"
    "${CMAKE_CURRENT_SOURCE_DIR}/msg/*.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
    ${PX4_MSG_FILES}
)

ament_package()
