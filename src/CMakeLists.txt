cmake_minimum_required(VERSION 3.20.0)

project(Extras)
set(target_name "utest")

include_directories($ENV{CPPUTEST_HOME}/include)
link_directories($ENV{CPPUTEST_HOME}/lib) 

add_definitions(-g -std=c++0x)

set(CMAKE_CXX_FLAGS "${CMAXE_CXX_FLAGS} -Wall")
set(sources)
set(testSources WorkTest.cpp)
add_executable(${target_name} testmain.cpp ${testSources} ${sources})

target_link_libraries(${target_name} CppUTest)
target_link_libraries(${target_name} pthread)

target_compile_features(${target_name} PUBLIC cxx_std_17)
