cmake_minimum_required(VERSION 3.3)

set(PROJECT downloads-manager)

project(PROJECT)

set(SRC
    src/main.c)

set(HDR)

set(SOURCE_FILES ${SRC} ${HDR})
list(SORT SOURCE_FILES)

# COMPILER FLAGS
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra -Werror \
    -Wno-unused-local-typedefs -target x86_64-apple-darwin")

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} \
    -DCHECK_RESULT_USED=\"__attribute__ ((warn_unused_result))\"")

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -D_GNU_SOURCE -D_FILE_OFFSET_BITS=64")

add_executable(${PROJECT} ${SOURCE_FILES})