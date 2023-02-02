cmake_minimum_required(VERSION 3.12)
set(PICO_SDK_PATH /home/shalidor/GitRepos/pico-sdk)
include(pico_sdk_import.cmake)

project(hello_world C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

add_compile_options(
    -Wno-format
    -Wno-unused-function
    -Wno-maybe-uninitalized
    )

pico_sdk_init()

add_executable(hello_world
        main.c
        )

# pull in common dependencies and additional spi hardware support
target_link_libraries(hello_world pico_stdlib hardware_spi)

# create map/bin/hex file etc.
# pico_add_extra_outputs(max7219_32x8_spi)
