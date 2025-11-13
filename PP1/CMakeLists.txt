cmake_minimum_required(VERSION 3.5)

cmake_policy(SET CMP0025 OLD)

project(mycpp)

# This can be read from ${PROJECT_NAME} after project() is called
project(mycpp LANGUAGES CXX)

add_executable(mycpp main.cpp)

set( CMAKE_INSTALL_RPATH_USE_LINK_PATH TRUE )

find_package( Curses REQUIRED )
include_directories( ${CURSES_INCLUDE_DIRS} )
target_link_libraries( mycpp ${CURSES_LIBRARIES} )
