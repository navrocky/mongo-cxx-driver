project(mongo-cxx-driver)

cmake_minimum_required(VERSION 2.8)

set(SRC_ROOT ${CMAKE_SOURCE_DIR}/../src)

set(mongoclient_version_major 1)
set(mongoclient_version_minor 0)
set(mongoclient_version_patch 0)

set(mongoclient_version "1.0.0-rc1-pre")
set(mongoclient_git_revision "-")

add_definitions(-DMONGO_EXPOSE_MACROS)

add_subdirectory(src)
