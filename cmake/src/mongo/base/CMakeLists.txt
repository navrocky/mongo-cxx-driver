set(TARGET mongo_base)

set(SRC_DIR ${SRC_ROOT}/mongo/base)

aux_source_directory(${SRC_DIR} SOURCES)

# generate error codes
find_package(PythonInterp REQUIRED)
add_custom_command(
    OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/error_codes.h ${CMAKE_CURRENT_BINARY_DIR}/error_codes.cpp
    COMMAND ${PYTHON_EXECUTABLE} ${SRC_DIR}/generate_error_codes.py ${SRC_DIR}/error_codes.err ${CMAKE_CURRENT_BINARY_DIR}/error_codes.h ${CMAKE_CURRENT_BINARY_DIR}/error_codes.cpp
)
set(SOURCES ${SOURCES}
    ${SRC_DIR}/error_codes.err
    ${CMAKE_CURRENT_BINARY_DIR}/error_codes.h
    ${CMAKE_CURRENT_BINARY_DIR}/error_codes.cpp
)

add_library(${TARGET} ${SOURCES})
