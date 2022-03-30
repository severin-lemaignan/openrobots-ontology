cmake_minimum_required(VERSION 3.0.2)
project(oro)

find_package(catkin REQUIRED)

catkin_package()

install(DIRECTORY share/ontologies
    DESTINATION ${CATKIN_GLOBAL_SHARE_DESTINATION}
)

