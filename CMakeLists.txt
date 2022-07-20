cmake_minimum_required(VERSION 3.3)
project(ss_twr_example_voxl)

include_directories(
    ./decadriver
    ./boards
    ./examples
)

add_executable(
    ss_twr_example_voxl
    ${CMAKE_CURRENT_SOURCE_DIR}/boards/voxl_dw1000.h
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_device.c
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_device_api.h 
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_params_init.c
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_param_types.h
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_range_tables.c
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_regs.h
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_types.h
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/deca_version.h
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/port/port_platform.h
    ${CMAKE_CURRENT_SOURCE_DIR}/deca_driver/port/port_platform.c
    ${CMAKE_CURRENT_SOURCE_DIR}/examples/ss_twr_resp/main.c
    ${CMAKE_CURRENT_SOURCE_DIR}/examples/ss_twr_resp/ss_resp_main.c
    /usr/include/voxl_io.h
)

target_link_libraries(
    ss_twr_example_voxl
    voxl_io
    m
)
