#cmake最小版本
cmake_minimum_required(VERSION 3.0.0)
#项目名
project(hello_library)

#生成执行文件
add_executable(hello_binary src/main.cpp)

#生成静态库
add_library(hello_library STATIC src/hello.cpp)

#文件目录
include_directories(hello_library
    PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_BINARY_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)

#targrt link library
target_link_libraries(hello_binary PRIVATE hello_library)

