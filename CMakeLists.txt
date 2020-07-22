cmake_minimum_required(VERSION 3.14)
project(Final)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES main.cpp ${SOURCE_FILES})

add_executable(Final main.cpp Final.h)

include_directories(/usr/local/include)


find_package(SFML 2.5 COMPONENTS system window graphics network audio REQUIRED)
include_directories(${SFML_INCLUDE_DIRS})
target_link_libraries(Final sfml-system sfml-window sfml-graphics sfml-audio sfml-network)

set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake_modules")
find_package(SFML REQUIRED system window graphics network audio)
if (SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(Final ${SFML_LIBRARIES})
endif()





