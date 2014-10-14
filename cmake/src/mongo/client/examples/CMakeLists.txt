remove_definitions(-DMONGO_EXPOSE_MACROS)
set(SRC_DIR ${SRC_ROOT}/mongo/client/examples)

################################################################################
set(TARGET client_example_first)
add_executable(${TARGET} ${SRC_DIR}/first.cpp)
target_link_libraries(${TARGET} mongo_client)

################################################################################
#set(TARGET client_example_first)
#add_executable(${TARGET} ${SRC_DIR}/first.cpp)
#target_link_libraries(${TARGET} mongo_client)

