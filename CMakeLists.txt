cmake_minimum_required(VERSION 3.10)

# 项目名称
project(securec LANGUAGES C)

MESSAGE(STATUS "This is BINARY dir " ${PROJECT_BINARY_DIR})
MESSAGE(STATUS "This is SOURCE dir "${PROJECT_SOURCE_DIR})
# 设置输出目录
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)

# 添加头文件搜索路径
include_directories(include)

# 设置编译选项
add_compile_options(-Wall -fPIC -g)

# 自动查找源文件
file(GLOB_RECURSE SOURCES "src/*.c")

# 生成静态库
add_library(securec STATIC ${SOURCES})

# 安装目标
install(TARGETS securec
        ARCHIVE DESTINATION lib)
install(DIRECTORY include/
        DESTINATION include
        FILES_MATCHING PATTERN "*.h")
