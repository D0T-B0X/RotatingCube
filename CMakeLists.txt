cmake_minimum_required(VERSION 3.31)
project(coordinate_systems)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GLFW REQUIRED glfw3)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(${PROJECT_NAME} ${CMAKE_SOURCE_DIR}/src/main.cpp ${CMAKE_SOURCE_DIR}/src/glad.c ${CMAKE_SOURCE_DIR}/src/stb_image_impl.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE ${GLFW_INCLUDE_DIRS})
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/include)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_BINARY_DIR})

target_link_libraries(${PROJECT_NAME} PRIVATE ${GLFW_LIBRARIES} dl)

target_compile_options(${PROJECT_NAME} PRIVATE ${GLFW_CFLAGS_OTHER})