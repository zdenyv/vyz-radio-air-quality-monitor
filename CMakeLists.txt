cmake_minimum_required(VERSION 3.20.0)

# Setup project name and languages
project(firmware LANGUAGES C ASM)

add_subdirectory(sdk)

# Increase task buffer, we use lot of sensors and versions in this project
target_compile_definitions(${CMAKE_PROJECT_NAME} PUBLIC TWR_SCHEDULER_MAX_TASKS=42)

# If you need to add some source files to the project add them to the "src" folder and update CMakeLists there
add_subdirectory(src)
