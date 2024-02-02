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

# generate and register with ament_index a file with the list of installed
# ontologies
set(list_ontologies "${CMAKE_BINARY_DIR}/list_ontologies")
file(REMOVE list_ontologies)

file(GLOB ontologies "share/ontologies/*")
foreach(ontology ${ontologies})
    get_filename_component(name ${ontology} NAME)
    # message(STATUS "Registering ${name}...")
    file(APPEND list_ontologies "ontologies/${name}\n")
endforeach()

ament_index_register_resource("ontologies" CONTENT_FILE list_ontologies)

ament_package()

