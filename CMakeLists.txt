cmake_minimum_required(VERSION 3.16)
project(
  parseReg
  VERSION 1.0
  LANGUAGES CXX)

# use HOST compiler to build gnuradio_4_0_parse_registrations
set(CMAKE_CXX_STANDARD 23)

add_executable(gnuradio4-block-parser parse_registrations.cpp)
target_compile_definitions(gnuradio4-block-parser PRIVATE GR4_PARSER_VERSION="${CMAKE_PROJECT_VERSION}")
install(TARGETS gnuradio4-block-parser)
