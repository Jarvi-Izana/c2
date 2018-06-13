project(chapterFirstExample)
cmake_minimum_required(VERSION 2.6)

include_directories($ENV{GMOCK_INCLUDE}/include $ENV{GTEST_INCLUDE}/include)
link_directories($ENV{GMOCK_LINK} $ENV{GTEST_LINK})
add_definitions(-std=c++0x)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall")

set(sources 
   main.cpp 
   CharUtil.cpp
   StringUtil.cpp)

set(testSources
    CharUtilTest.cpp
    SoundexTest.cpp
    StringUtilTest.cpp)

add_executable(mytest ${testSources} ${sources})

target_link_libraries(mytest pthread)
target_link_libraries(mytest gmock)
target_link_libraries(mytest gtest)

