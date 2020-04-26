cmake_minimum_required(VERSION 2.8)
enable_language(ASM)

project(template)

find_package(CMSIS REQUIRED)

include_directories(${CMAKE_CURRENT_SOURCE_DIR} ${CMSIS_INCLUDE_DIRS})

set(PROJECT_SOURCES ./src/main.c)

set(STM32_LINKER_SCRIPT ${CMSIS_LINKER_SCRIPT})

add_executable(${CMAKE_PROJECT_NAME} ${PROJECT_SOURCES} ${CMSIS_SOURCES})

stm32_set_target_properties(${CMAKE_PROJECT_NAME})
stm32_add_hex_bin_targets(${CMAKE_PROJECT_NAME})
stm32_print_size_of_targets(${CMAKE_PROJECT_NAME})
