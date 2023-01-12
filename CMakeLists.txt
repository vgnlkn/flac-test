cmake_minimum_required(VERSION 3.3)
project(flac-test)

set(CMAKE_SUPPRESS_REGENERATION true)

include(conan/conanbuildinfo.cmake)
add_compile_definitions(FLAC__NO_DLL)

link_directories(${CONAN_LIB_DIRS})

add_executable(Decoder "src/decoder.cpp")
add_executable(Encoder "src/encoder.cpp")


target_include_directories(Decoder PUBLIC ${CONAN_INCLUDE_DIRS})
target_link_libraries(Decoder ${CONAN_LIBS})

target_include_directories(Encoder PUBLIC ${CONAN_INCLUDE_DIRS})
target_link_libraries(Encoder ${CONAN_LIBS})
