cmake_minimum_required(VERSION 3.20)
project(dudo VERSION 0.1)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED true)

set(EXECUTABLE_SRC ${CMAKE_CURRENT_SOURCE_DIR}/src)

list(APPEND EXECUTABLE_LIST 
    ${EXECUTABLE_SRC}/main.cpp
    ${EXECUTABLE_SRC}/class1.cpp
    
)

set(Catch2_DIR "lib/cmake/Catch2")
find_package(Catch2 3 REQUIRED)
add_executable(tests tests/test.cpp)
target_link_libraries(tests PRIVATE Catch2::Catch2WithMain)

add_executable(dudo ${EXECUTABLE_LIST})
target_include_directories(dudo PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
