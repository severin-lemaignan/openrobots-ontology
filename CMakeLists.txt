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

file(GLOB ontologies "share/ontologies/*")

foreach(ontology ${ontologies})
    get_filename_component(name ${ontology} NAME)
    ament_index_register_resource("ontologies" CONTENT_FILE ${ontology} PACKAGE_NAME ${name})
endforeach()

ament_package()

