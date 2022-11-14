cmake_minimum_required(VERSION 3.0.2)
project(ytlab_ros_example)
# add_compile_options(-std=c++11)

find_package(catkin REQUIRED
    message_filters
    roscpp
    std_srvs
    tf
    dynamic_reconfigure
    nav_msgs
    std_srvs
    pcl_conversions
    pcl_ros
    laser_geometry
)
catkin_package(
    CATKIN_DEPENDS
        roscpp
        dynamic_reconfigure
        tf
  CATKIN_DEPENDS nav_msgs std_srvs
)
include_directories(${catkin_INCLUDE_DIRS})
# add_message_files(
#   FILES
#   Message1.msg
#   Message2.msg
# )

# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

# generate_messages(
#   DEPENDENCIES
#   std_msgs  # Or other packages containing msgs
# )

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES ros_pkg_template
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

include_directories(
# include
# ${catkin_INCLUDE_DIRS}
)
