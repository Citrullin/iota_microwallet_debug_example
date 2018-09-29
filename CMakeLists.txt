cmake_minimum_required(VERSION 3.0)
project(riot_test)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED TRUE)

set(SOURCE_FILES
        main.c)

include_directories(
        iota/src/iota
        iota/src/keccak
        iota/src/
)

add_executable(riot_test ${SOURCE_FILES})
target_link_libraries(riot_test ${CMAKE_SOURCE_DIR}/iota/libiota_wallet.a)