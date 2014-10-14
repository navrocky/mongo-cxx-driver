#set(TARGET mongo_client)

# test for big endian
include(TestBigEndian)
test_big_endian(BIG_ENDIAN)
if(${BIG_ENDIAN})
    set(mongoclient_byte_order "#define MONGO_BYTE_ORDER 4321")
else()
    set(mongoclient_byte_order "#define MONGO_BYTE_ORDER 1234")
endif()

configure_file(${SRC_ROOT}/mongo/config.h.in ${CMAKE_CURRENT_BINARY_DIR}/config.h )
configure_file(${SRC_ROOT}/mongo/version.h.in ${CMAKE_CURRENT_BINARY_DIR}/version.h )

include_directories(${CMAKE_BINARY_DIR}/src)
include_directories(${SRC_ROOT}/third_party/gtest-1.7.0/include)

add_subdirectory(base)
add_subdirectory(bson)
add_subdirectory(client)

