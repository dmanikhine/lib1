cmake_minimum_required (VERSION 3.20)

set (project_name "lib1")

project (${project_name})
add_library(${project_name} "")
add_subdirectory (src)
set_target_properties(${project_name} PROPERTIES
  ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
  LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
  RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
set_target_properties(${project_name} PROPERTIES PUBLIC_HEADER "src/lib1.h")
install(TARGETS ${project_name})
