cmake_minimum_required(VERSION 2.8)

project(xor-systemc CXX)

set(CMAKE_CXX_STANDARD 11) # This is equal to QMAKE_CXX_FLAGS += -std=c++0x
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set (CMAKE_PREFIX_PATH $ENV{SYSTEMC_HOME})

find_package(SystemCLanguage CONFIG REQUIRED)
set (CMAKE_CXX_STANDARD ${SystemC_CXX_STANDARD})


# own implementation
include_directories(./src)
aux_source_directory(./src XOR_SOURCES)
add_executable(${PROJECT_NAME} ${XOR_SOURCES})

target_link_libraries(${PROJECT_NAME} SystemC::systemc)
