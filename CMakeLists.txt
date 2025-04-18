cmake_minimum_required( VERSION 3.16)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(PICO_SDK_PATH "/home/dpoyesac/Projects/pico/pico-sdk")
include(pico_sdk_import.cmake)

project(pico-ssd1306 C CXX ASM)

pico_sdk_init()

add_library(pico-ssd1306 
    ssd1306.h
    ssd1306.c
    )

target_link_libraries(pico-ssd1306 
        pico_stdlib
        hardware_i2c
        )

target_include_directories(pico-ssd1306 PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")
