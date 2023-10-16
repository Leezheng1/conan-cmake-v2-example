cmake_minimum_required(VERSION 3.24)

# 设置C++标准
set(CMAKE_CXX_STANDARD 14)

# 工程名称
project(example-libcurl)

# Module模式下，会首先在CMAKE_MODULE_PATH路径下进行库cmake文件的搜索，如果没找到，则会采取Config模式
# set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

find_package(CURL REQUIRED)

add_executable(${PROJECT_NAME} src/main.cc)

target_link_libraries(${PROJECT_NAME} PRIVATE CURL::libcurl)
