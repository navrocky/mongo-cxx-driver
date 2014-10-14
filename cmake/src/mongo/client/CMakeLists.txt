set(TARGET mongo_client)

set(SRC_DIR ${SRC_ROOT}/mongo/client)

#aux_source_directory(${SRC_DIR} SOURCES)

set(SOURCES
    ${SRC_DIR}/init.h
    ${SRC_DIR}/init.cpp
    ${SRC_DIR}/dbclient.h
    ${SRC_DIR}/dbclient.cpp
    ${SRC_DIR}/options.h
    ${SRC_DIR}/options.cpp
)

add_library(${TARGET} ${SOURCES})
target_link_libraries(${TARGET} ${Boost_LIBRARIES} mongo_bson mongo_util mongo_logger)

add_subdirectory(examples)
