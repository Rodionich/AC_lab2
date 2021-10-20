cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)

project(ac_lab2)

set(SOURCE_EXE src/main.cpp)
set(SOURCE_LIB src/calculator.cpp)
set(SOURCE_HEADER include/calculator.h)

add_library(calculator
  ${SOURCE_LIB}
  ${SOURCE_HEADER}
)

target_include_directories(calculator
    PUBLIC
		"include"
)

add_executable(main
    ${SOURCE_EXE}
)

target_link_libraries(main calculator)
