cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_C_STANDARD 11)

set(CMAKE_CXX_FLAGS_DEBUG  ${CMAKE_CXX_FLAGS} "-g -Wall -Wextra -O0")
set(CMAKE_CXX_FLAGS_RELEASE ${CMAKE_CXX_FLAGS} "-g -Wall -O3")

set(SOURCES
        PacketDoubler.c
        )
add_executable(PacketDoubler ${SOURCES})
target_link_libraries(PacketDoubler libpcap.a libnet.a)
