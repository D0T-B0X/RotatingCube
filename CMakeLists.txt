cmake_minimum_required(VERSION 3.31)
project(coordinate_systems)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GLFW REQUIRED glfw3)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(SHADER_DIR "${CMAKE_SOURCE_DIR}/shaders")
set(VERTEX_SHADER "${SHADER_DIR}/vertex.glsl")
set(FRAGMENT_SHADER "${SHADER_DIR}/fragment.glsl")
set(ASSETS_DIR "${CMAKE_SOURCE_DIR}/assets")
set(AWESOME_FACE_IMG "${ASSETS_DIR}/awesomeface.png")
set(CONTAINER_IMG "${ASSETS_DIR}/container.jpg")

configure_file(
    ${CMAKE_SOURCE_DIR}/config.h.in
    ${CMAKE_BINARY_DIR}/config.h
)

add_executable(${PROJECT_NAME} ${CMAKE_SOURCE_DIR}/src/main.cpp ${CMAKE_SOURCE_DIR}/src/glad.c ${CMAKE_SOURCE_DIR}/src/stb_image_impl.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE ${GLFW_INCLUDE_DIRS})
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/include)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_BINARY_DIR})

target_link_libraries(${PROJECT_NAME} PRIVATE ${GLFW_LIBRARIES} dl)

target_compile_options(${PROJECT_NAME} PRIVATE ${GLFW_CFLAGS_OTHER})