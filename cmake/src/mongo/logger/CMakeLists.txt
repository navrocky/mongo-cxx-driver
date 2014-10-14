set(TARGET mongo_logger)

#include_directories(${SRC_ROOT}/third_party/gtest-1.7.0/include)

set(SRC_DIR ${SRC_ROOT}/mongo/logger)
#include_directories(${CMAKE_BINARY_DIR}/src)

aux_source_directory(${SRC_DIR} SOURCES)
#aux_source_directory(${SRC_DIR}/net SOURCES)
#aux_source_directory(${SRC_DIR}/concurrency SOURCES)

# generate error codes
#find_package(PythonInterp REQUIRED)
#add_custom_command(
#    OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/error_codes.h ${CMAKE_CURRENT_BINARY_DIR}/error_codes.cpp
#    COMMAND ${PYTHON_EXECUTABLE} ${SRC_DIR}/generate_error_codes.py ${SRC_DIR}/error_codes.err ${CMAKE_CURRENT_BINARY_DIR}/error_codes.h ${CMAKE_CURRENT_BINARY_DIR}/error_codes.cpp
#)
#set(SOURCES ${SOURCES}
#    ${SRC_DIR}/error_codes.err
#    ${CMAKE_CURRENT_BINARY_DIR}/error_codes.h
#    ${CMAKE_CURRENT_BINARY_DIR}/error_codes.cpp
#)

#set(SOURCES
#    ${SRC_DIR}/net/hostandport.h
#    ${SRC_DIR}/net/hostandport.cpp
#    ${SRC_DIR}/assert_util.h
#    ${SRC_DIR}/assert_util.cpp
#)

add_library(${TARGET} ${SOURCES})
#target_link_libraries(${TARGET} mongo_base)
