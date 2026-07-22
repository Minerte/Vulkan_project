cmake_minimum_required(VERSION 3.20)

project(
    Vulkan_project
    VERSION 0.0.1
    LANGUAGES CXX
)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(Vulkan REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)

file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS
    # May be better for big project to do
    # src/FileName.cpp so less cpu cycle 
    src/*.cpp
    src/*.c
)

add_executable(${PROJECT_NAME}
    ${SOURCES}
)

# ASSETS

# add_custom_command(TARGET ${PROJECT_NAME} POST_BUILD
#     COMMAND ${CMAKE_COMMAND} -E copy_directory
#         ${CMAKE_SOURCE_DIR}/assets
#         $<TARGET_FILE_DIR:${PROJECT_NAME}>/assets
# )

# SHADERS

# find_program(GLSLC glslc REQUIRED)

# file(GLOB_RECURSE SHADERS CONFIGURE_DEPENDS
#     shaders/*.vert
#     shaders/*.frag
#     shaders/*.comp
# )

# foreach(SHADER ${SHADERS})

#     get_filename_component(FILE_NAME ${SHADER} NAME)

#     add_custom_command(
#         TARGET ${PROJECT_NAME}
#         POST_BUILD
#         COMMAND ${GLSLC}
#             ${SHADER}
#             -o
#             $<TARGET_FILE_DIR:${PROJECT_NAME}>/${FILE_NAME}.spv
#         DEPENDS ${SHADER}
#     )

# endforeach()

target_include_directories(${PROJECT_NAME}
    PRIVATE
        include
            ${CMAKE_SOURCE_DIR}/include
)

target_link_libraries(${PROJECT_NAME}
    PRIVATE
        Vulkan::Vulkan
        glfw
        glm::glm
)

if(MSVC)
    target_compile_options(${PROJECT_NAME} PRIVATE /W4)
else()
    target_compile_options(${PROJECT_NAME}
        PRIVATE
        -Wall
        -Wextra
        -Wpedantic
    )
endif()