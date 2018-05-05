cmake_minimum_required(VERSION 3.1)
set(CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} ${CMAKE_BINARY_DIR}/xtl ${CMAKE_BINARY_DIR}/json)
project(demo)

add_executable(demo main.cpp)
target_link_libraries(demo PRIVATE xtensor)
set_target_properties(demo PROPERTIES
	CXX_STANDARD 14
	CXX_STANDARD_REQUIRED YES
	CXX_EXTENSIONS NO
)
set(JSON_BuildTests OFF CACHE BOOL "Build the unit tests when BUILD_TESTING is enabled.")
add_subdirectory(json)
add_subdirectory(xtl)
add_subdirectory(xtensor)
