cmake_minimum_required(VERSION 3.0.0)
project(LearnVSCode VERSION 0.1.0)

SET(OUTPUT_PATH "" CACHE STRING "Combination of OS and Compiler from CommandLine e.g. -D windows_gcc")

STRING(REPLACE "BuildSystem" "CASAL2" PROJECT_HOME_DIRECTORY ${CMAKE_HOME_DIRECTORY})

MESSAGE("-- Root Folder: ${PROJECT_HOME_DIRECTORY}")
MESSAGE("-- Output Path: ${OUTPUT_PATH}")
MESSAGE("-- DEBUG: ${DEBUG}")
MESSAGE("-- RELEASE: ${RELEASE}")
MESSAGE("-- TEST: ${TEST}")

IF (DEBUG EQUAL 1)
MESSAGE("-- DEBUG MODE ENABLED")
ENDIF ()
IF (RELEASE EQUAL 1)
MESSAGE("-- RELEASE MODE ENABLED")
ENDIF ()


MESSAGE("Third-Party Directory: ${CMAKE_HOME_DIRECTORY}/bin/${OUTPUT_PATH}/thirdparty/include")
MESSAGE("Source Code Folder: ${PROJECT_HOME_DIRECTORY}")


add_executable(main main.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

