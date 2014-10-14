project(mongo-cxx-driver)

cmake_minimum_required(VERSION 2.8)

set(SRC_ROOT ${CMAKE_SOURCE_DIR}/../src)

set(mongoclient_version_major 1)
set(mongoclient_version_minor 0)
set(mongoclient_version_patch 0)

set(mongoclient_version "1.0.0-rc1-pre")
set(mongoclient_git_revision "-")

add_definitions(-DMONGO_EXPOSE_MACROS)
add_definitions(-DSTATIC_LIBMONGOCLIENT)

if(MINGW)
    add_definitions(-D_WIN32_WINNT=0x0502)
    add_definitions(-DNTDDI_VERSION=0x05020000)
endif()

if(WIN32)
    add_definitions(-D_UNICODE)
    add_definitions(-DUNICODE)
    add_definitions(-DNOMINMAX)
endif()

add_subdirectory(src)
