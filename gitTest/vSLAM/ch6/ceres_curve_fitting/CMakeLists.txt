cmake_minimum_required( VERSION 2.8 )

project( ceres_curve_fitting )

set( CMAKE_BUILD_TYPE "Release" )
set( CMAKE_CXX_FLAGS "-std=c++11" )

list( APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules )

find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )

find_package( Ceres REQUIRED )
include_directories( ${Ceres_INCLUDE_DIRS} )

add_executable( curve_fitting main.cpp )
target_link_libraries( curve_fitting ${OpenCV_LIBS} ${CERES_LIBRARIES} )
