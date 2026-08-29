cmake_minimum_required(VERSION 3.16)
project(
  parseReg
  VERSION 0.1
  LANGUAGES CXX)

# use HOST compiler to build gnuradio_4_0_parse_registrations
set(CMAKE_CXX_STANDARD 23)

add_executable(gnuradio_4_0_parse_registrations parse_registrations.cpp)
