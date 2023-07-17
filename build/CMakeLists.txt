cmake_minimum_required(VERSION 2.8)

project(hello_world)

set(BIN ../bin)
set(SRC ../src)
set(MAIN_DIR ${SRC}/main)
set(PRINT_DIR ${SRC}/print)
#set(SOURCE_EXE ${SRC}/main/main.c)
#set(SOURCE_LIB ${SRC}/print.c)

#file(GLOB HEADERS)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${BIN})

add_library(l_print STATIC ${PRINT_DIR}/print.c)

include_directories(${PRINT_DIR})

add_executable(dsa ${MAIN_DIR}/main.c)

target_link_libraries(dsa l_print)
