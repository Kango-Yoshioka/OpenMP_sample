cmake_minimum_required(VERSION 3.22)
project(OpenMP_sample)

set(CMAKE_CXX_STANDARD 14)

file(GLOB MY_SOURCE src/*.cpp)

add_executable(${PROJECT_NAME} ${MY_SOURCE})

find_package(OpenMP)
if(OPENMP_CXX_FOUND)
    # add flags for OpenMP
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
    set(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} ${OpenMP_SHARED_LINKER_FLAGS}")
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} ${OpenMP_EXE_LINKER_FLAGS}")
endif()