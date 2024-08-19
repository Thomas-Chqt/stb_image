# ---------------------------------------------------
# CMakeLists.txt
#
# Author: Thomas Choquet <semoir.dense-0h@icloud.com>
# Date: 2024/08/19 16:16:50
# ---------------------------------------------------

cmake_minimum_required(VERSION 3.16)

project(stb_image LANGUAGES CXX)

option(BUILD_SHARED_LIBS "Build using shared libraries" OFF)

add_library(stb_image ${STBIMG_LIBRARY_TYPE})
set_target_properties(stb_image PROPERTIES CXX_STANDARD 17 CXX_STANDARD_REQUIRED ON)

file(GLOB_RECURSE STBIMG_SRCS "src/stb_image.cpp" "include/stb_image/stb_image.h")
target_sources(stb_image PRIVATE "${STBIMG_SRCS}")

target_include_directories(stb_image PRIVATE "src" PUBLIC "include")

