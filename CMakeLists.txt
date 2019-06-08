cmake_minimum_required(VERSION 2.8.3)
project(cpr_catkin)

find_package(catkin REQUIRED)

include(ExternalProject)

file(MAKE_DIRECTORY ${CATKIN_DEVEL_PREFIX}/include)

ExternalProject_Add(cpr
  GIT_REPOSITORY "https://github.com/whoshuu/cpr.git"
  CMAKE_CACHE_ARGS "-DCMAKE_POSITION_INDEPENDENT_CODE:BOOL=true"
  INSTALL_COMMAND bash "-c" "cp -r ../cpr/include/* ${CATKIN_DEVEL_PREFIX}/include && cp lib/libcpr.a ${CATKIN_DEVEL_PREFIX}/lib"#
)

catkin_package(
  INCLUDE_DIRS
    ${CATKIN_DEVEL_PREFIX}/include
  LIBRARIES
    cpr
  CATKIN_DEPENDS
)
