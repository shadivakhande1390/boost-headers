# About
This repository contains a set of header files from Boost. Can be useful when using header only [libraries.](https://www.boost.org/doc/libs/1_77_0/more/getting_started/windows.html#header-only-libraries)
# How to use
You can easily include the headers using CMake.

```
cmake_minimum_required(VERSION 3.11)
include(FetchContent)

project(YOUR_PROJECT)
add_executable(YOUR_EXECUTABLE main.cpp)

FetchContent_Declare(
  boost_headers
  GIT_REPOSITORY https://github.com/FQLT/boost-headers.git
  GIT_TAG        d1683ad28bbefe33e652a14322e2de11513d9bfc # release-1.77.0
)
FetchContent_MakeAvailable(boost_headers)

FetchContent_GetProperties(boost_headers)
if(NOT boost_headers_POPULATED)
  FetchContent_Populate(boost_headers)
  add_subdirectory(${boost_headers_SOURCE_DIR} ${boost_headers_BINARY_DIR})
endif()

target_link_libraries(YOUR_EXECUTABLE boost_headers)
```
