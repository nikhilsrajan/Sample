cmake_minimum_required(VERSION 3.5)
project(<Project>)

set(SRC_DIR code/src)
set(HDR_DIR code/include)

set(
    DIRS
    ${SRC_DIR}
    ${HDR_DIR}
)

include_directories(${DIRS})

set(
    SRCS
    ${SRC_DIR}/main.cpp
)

set(
    HDRS
    ${HDR_DIR}/test.hpp
)

set(
    SOURCE_LIST
    ${SRCS}
    ${HDRS}
)

add_library(<Project> SHARED ${SOURCE_LIST})

add_executable(<Project>Test ${SRC_DIR}/main.cpp)
target_link_libraries(
    <Project>Test
    PRIVATE
    <Project>
)
