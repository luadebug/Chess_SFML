cmake_minimum_required(VERSION 3.29)
project(Chess_SFML)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} "$ENV{VCPKG_ROOT}/installed/x86-windows")

find_package(SFML 2.6.1 COMPONENTS system window graphics CONFIG REQUIRED)



add_executable(Chess_SFML
    main.cpp
    main.hpp)

target_link_libraries(Chess_SFML PRIVATE sfml-system sfml-window sfml-graphics)
file(COPY
        ${CMAKE_SOURCE_DIR}/resources
        DESTINATION
        ${CMAKE_BINARY_DIR}
)
