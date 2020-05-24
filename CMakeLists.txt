# Require 3.3 and set policy CMP0057 for IN_LIST operator support
cmake_minimum_required(VERSION 3.3)
cmake_policy(SET CMP0057 NEW)
project(onnx-mlir-dialect)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

include(MLIR.cmake)

set(CMAKE_CXX_STANDARD 14)
set(INCLUDE_ONNX_ML OFF)

message(STATUS "INCLUDE_ONNX_ML Dialect " ${INCLUDE_ONNX_ML})

add_subdirectory(src)
