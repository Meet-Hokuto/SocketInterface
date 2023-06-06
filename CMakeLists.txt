cmake_minimum_required(VERSION 3.0.2)
project(SocketInterface)
add_compile_options(-std=c++17)

include_directories(
  ${PROJECT_SOURCE_DIR}/include
)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)

add_library(${PROJECT_NAME} SHARED
src/SocketBase.cpp
)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/Examples/test)

add_executable(udp_test
Examples/udp_test.cpp)
target_link_libraries(udp_test ${PROJECT_NAME})