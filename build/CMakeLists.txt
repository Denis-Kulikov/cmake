cmake_minimum_required(VERSION 2.8)

project(hello_world)

set(SRC ../src)
set(MAIN_DIR ${SRC}/main)
set(PRINT_DIR ${SRC}/print)
#set(SOURCE_EXE ${SRC}/main/main.c)
#set(SOURCE_LIB ${SRC}/print.c)

#file(GLOB HEADERS)

add_library(l_print STATIC ${PRINT_DIR}/print.c ${PRINT_DIR}/print.h)

include_directories(${PRINT_DIR})

add_executable(main ${MAIN_DIR}/main.c ${PRINT_DIR}/print.h)

target_link_libraries(main l_print)
