cmake_minimum_required(VERSION 3.10)

# set the project name and version
project(Tutorial VERSION 1.14)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# configure_file的作用将一份文件拷贝到另一个位置并修改它的内容，
# 使得在代码中使用CMake中定义的变量 
configure_file(TutorialConfig.h.in TutorialConfig.h)

# add the executable
add_executable(Tutorial tutorial.cxx)

# 指定项目编译的时候需要include的文件路径，PROJECT_BINARY_DIR变量为编译发生的目录，也就是make执行的目录，PROJECT_SOURCE_DIR为工程所在的目录 
# target_include_directories官方文档：https://cmake.org/cmake/help/v3.3/command/target_include_directories.html 
target_include_directories(Tutorial PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           )