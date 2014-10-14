set(TARGET mongo_client)

find_package(Boost REQUIRED)
include_directories(${Boost_INCLUDE_DIRS})

set(SRC_DIR ${SRC_ROOT}/mongo/client)

aux_source_directory(${SRC_DIR} SOURCES)

add_library(${TARGET} ${SOURCES})
