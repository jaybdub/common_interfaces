cmake_minimum_required(VERSION 3.5)

project(geometry_msgs)

if(NOT WIN32)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra")
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

set(msg_files
  "msg/Point.msg"
  "msg/Point32.msg"
  "msg/PointStamped.msg"
  "msg/Polygon.msg"
  "msg/PolygonStamped.msg"
  "msg/Pose.msg"
  "msg/Pose2D.msg"
  "msg/PoseArray.msg"
  "msg/PoseStamped.msg"
  "msg/PoseWithCovariance.msg"
  "msg/PoseWithCovarianceStamped.msg"
  "msg/Quaternion.msg"
  "msg/QuaternionStamped.msg"
  "msg/Transform.msg"
  "msg/TransformStamped.msg"
  "msg/Twist.msg"
  "msg/TwistStamped.msg"
  "msg/TwistWithCovariance.msg"
  "msg/TwistWithCovarianceStamped.msg"
  "msg/Vector3.msg"
  "msg/Vector3Stamped.msg"
  "msg/Wrench.msg"
  "msg/WrenchStamped.msg"
)
rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES std_msgs
  ADD_LINTER_TESTS
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
