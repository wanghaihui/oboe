cmake_minimum_required(VERSION 3.4.1)

set(GOOGLETEST_ROOT ${ANDROID_NDK}/sources/third_party/googletest)
add_library(gtest STATIC ${GOOGLETEST_ROOT}/src/gtest_main.cc ${GOOGLETEST_ROOT}/src/gtest-all.cc)
target_include_directories(gtest PRIVATE ${GOOGLETEST_ROOT})
target_include_directories(gtest PUBLIC ${GOOGLETEST_ROOT}/include)

include_directories(../include)
add_executable(testOboe testUtilities.cpp ../src/common/Utilities.cpp)
target_link_libraries(testOboe gtest)