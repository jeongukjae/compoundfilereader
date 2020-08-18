cmake_minimum_required(VERSION 3.0)

project(compoundfilereader VERSION 0.1.0 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(${PROJECT_SOURCE_DIR}/src/include)

option(BUILD_SAMPLES "Build sample codes" OFF)

if(BUILD_SAMPLES)
  add_executable(cfb samples/cfb/cfb.cpp)
  add_executable(ieot samples/IEOpenedTabParser/openedtab.cpp)
endif()
