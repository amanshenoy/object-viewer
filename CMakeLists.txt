cmake_minimum_required (VERSION 3.16)

project (Object-Viewer)

set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Werror -std=c++17")
set (source_dir "${PROJECT_SOURCE_DIR}/src/")

find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)

file (GLOB source_files "${source_dir}/*.cpp" "${source_dir}/dependancies/*.cpp" "${source_dir}/dependancies/*/*.cpp")

add_executable (object-viewer ${source_files})
target_link_libraries(object-viewer glfw)
target_link_libraries(object-viewer OpenGL::GL)
target_link_libraries(object-viewer GLEW)
