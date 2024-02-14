cmake_minimum_required(VERSION 3.8.0)
project(oro)

find_package(ament_cmake REQUIRED)

# this CMake file registers all provided ontologies with the ament_index
# resource index, under the resource name 'ontologies'.
#
# Available ontologies can then be retrieved at runtime with e.g.
#
# >>> import ament_index_python as aip
# >>> aip.get_resources("ontologies")

install(DIRECTORY share/ontologies DESTINATION share/${PROJECT_NAME} )

file(GLOB_RECURSE ontologies RELATIVE ${CMAKE_SOURCE_DIR}/share "share/ontologies/*")
list(JOIN ontologies "\n" list_ontologies)

ament_index_register_resource("ontologies" CONTENT "${list_ontologies}")

ament_package()

