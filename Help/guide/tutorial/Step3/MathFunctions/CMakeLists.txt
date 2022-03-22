add_library(MathFunctions mysqrt.cxx)
# CMAKE_CURRENT_SOURCE_DIR 当前正在处理的CMakeLists所在的目录
target_include_directories(MathFunctions
          INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}
        )