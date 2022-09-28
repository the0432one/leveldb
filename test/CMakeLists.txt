cmake_minimum_required(VERSION 3.0.0)
project(cmtest VERSION 0.1.0)

include(CTest)
enable_testing()

include_directories(${CMAKE_SOURCE_DIR}/../include)
add_executable(cmtest test.cpp)
target_link_libraries(cmtest ${CMAKE_SOURCE_DIR}/lib/libleveldb.a) 

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
target_link_libraries(cmtest pthread)