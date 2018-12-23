cmake_minimum_required(VERSION 3.0)
project(riot_test)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED TRUE)

find_package(Threads)

set(SOURCE_FILES
        iota/src/iota/transfers.c
        iota/src/iota/bundle.c
        iota/src/iota/addresses.c
        iota/src/iota/signing.c
        iota/src/iota/kerl.c
        main.c)

include_directories(
        iota/src/iota
        iota/src/keccak
        iota/src/
)

execute_process(
        COMMAND bash "-c" "build_iota.sh"
        OUTPUT_VARIABLE FOO
)

add_executable(riot_test ${SOURCE_FILES})
target_link_libraries (riot_test ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries(riot_test ${CMAKE_SOURCE_DIR}/iota/build/libiota.a)