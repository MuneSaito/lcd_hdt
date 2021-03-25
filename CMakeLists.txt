cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(lcd_1602_i2c_project C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
pico_sdk_init()

add_executable(lcd_1602_i2c
        lcd_1602_i2c.c
        )

# Pull in our (to be renamed) simple get you started dependencies
target_link_libraries(lcd_1602_i2c pico_stdlib hardware_i2c)

# enable usb output, disable uart output
pico_enable_stdio_usb(lcd_1602_i2c 1)
pico_enable_stdio_uart(lcd_1602_i2c 0)

# create map/bin/hex file etc.
pico_add_extra_outputs(lcd_1602_i2c)

# add url via pico_set_program_url
#example_auto_set_url(lcd_1602_i2c)
