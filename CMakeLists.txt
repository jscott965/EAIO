#-------------------------------------------------------------------------------------------
# Copyright (C) Electronic Arts Inc.  All rights reserved.
#-------------------------------------------------------------------------------------------
cmake_minimum_required(VERSION 3.1)
project(EAIO CXX)

#-------------------------------------------------------------------------------------------
# Compiler Flags
#-------------------------------------------------------------------------------------------
set (CMAKE_MODULE_PATH "${CMAKE_MODULE_PATH};${CMAKE_CURRENT_SOURCE_DIR}/test/packages/EASTL/scripts/CMake")
include(CommonCppFlags)

#-------------------------------------------------------------------------------------------
# Library definition
#-------------------------------------------------------------------------------------------
file(GLOB EAIO_SOURCES "source/*.cpp")
add_library(EAIO ${EAIO_SOURCES})

#-------------------------------------------------------------------------------------------
# Defines
#-------------------------------------------------------------------------------------------
add_definitions(-D_CHAR16T)
add_definitions(-D_CRT_SECURE_NO_WARNINGS)
add_definitions(-D_SCL_SECURE_NO_WARNINGS)
add_definitions(-DEASTL_OPENSOURCE=1)
add_definitions(-DUTF_USE_EATRACE=0)
add_definitions(-DUTF_USE_EAASSERT=1)

#-------------------------------------------------------------------------------------------
# Include dirs
#-------------------------------------------------------------------------------------------
target_include_directories(EAIO PUBLIC include)

#-------------------------------------------------------------------------------------------
# Dependencies
#-------------------------------------------------------------------------------------------
if (NOT TARGET EASTL)
    add_subdirectory(test/packages/EASTL)
endif()
if (NOT TARGET EAAssert)
    add_subdirectory(test/packages/EASTL/test/packages/EAAssert)
endif()

target_link_libraries(EAIO EASTL EAAssert)
