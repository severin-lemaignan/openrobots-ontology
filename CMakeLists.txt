cmake_minimum_required(VERSION 3.8.0)
project(oro)

find_package(ament_cmake REQUIRED)

# this CMake file registers all provided ontologies with the ament_index
# resource index, under the resource name 'ontologies'.
#
# Available ontologies can then be retrieved at runtime with e.g.
#
# >>> import ament_index_python as aip
# >>> aip.get_resources("ontology")
# {'oro': '<path>'}
# >>> oro = aip.get_resource("ontology", "oro")
# >>> oro
# ('ontologies/oro.owl\nontologies/oro2.owl', '<path>')
#
# >>> oro_list, path = oro
# >>> for ontology in oro_list.split("\n"):
# ...     print(os.path.join(path, ontology))


install(DIRECTORY share/ontologies DESTINATION share/${PROJECT_NAME} )

file(GLOB_RECURSE ontologies RELATIVE ${CMAKE_SOURCE_DIR}/share "share/ontologies/*")
list(JOIN ontologies "\n" list_ontologies)

ament_index_register_resource("ontology" CONTENT "${list_ontologies}")

ament_package()

