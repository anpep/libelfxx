cmake_minimum_required (VERSION 2.6)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include/libelf++)

if (NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE DEBUG)
endif()
set(CMAKE_CXX_FLAGS "-std=gnu++11 -Wall -Wno-unused-local-typedefs -static-libstdc++ -static-libgcc -D__STDC_FORMAT_MACROS")
set(CMAKE_CXX_FLAGS_DEBUG "-g3 -O0")
set(CMAKE_CXX_FLAGS_DEBUGASAN "-g3 -O0 -fsanitize=address -ldl -static-libasan")
set(CMAKE_CXX_FLAGS_RELEASE "-O2 -flto -g -ffat-lto-objects")

add_subdirectory(src)
