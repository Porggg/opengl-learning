# GLAD
add_library(glad STATIC glad.c)
target_include_directories(glad PUBLIC ${CMAKE_SOURCE_DIR}/include)
set_target_properties(glad PROPERTIES POSITION_INDEPENDENT_CODE ON)

# Exécutable principal
add_executable(learn learn.cpp)
target_include_directories(learn PRIVATE ${CMAKE_SOURCE_DIR}/include)
target_link_options(learn PRIVATE "-no-pie")
target_link_libraries(learn glad ${GLFW3_LIBRARIES})