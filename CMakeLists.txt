
cmake_minimum_required (VERSION 3.16.3)

project(opengl-learning CXX)
enable_language(C)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_CXX_FLAGS "-Wall")

# filepath: /home/aubin/Documents/Code/opengl-learning/CMakeLists.txt
find_package(PkgConfig REQUIRED)
pkg_check_modules(GLFW3 REQUIRED glfw3)

include_directories(${GLFW3_INCLUDE_DIRS})
link_directories(${GLFW3_LIBRARY_DIRS})

include_directories(${CMAKE_SOURCE_DIR}/include)
# include_directories(${CMAKE_SOURCE_DIR}/../../../App/Include)


add_subdirectory(src)
# Cible pour générer la documentation avec Doxygen
# find_package(Doxygen REQUIRED)
# set(DOXYGEN_IN ${CMAKE_SOURCE_DIR}/docu/Doxyfile)
# set(DOXYGEN_OUT ${CMAKE_BINARY_DIR}/docu/)

# add_custom_target(doc
#     COMMAND ${DOXYGEN_EXECUTABLE} ${DOXYGEN_IN}
#     WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}/docu
#     COMMENT "Génération de la documentation Doxygen"
# )