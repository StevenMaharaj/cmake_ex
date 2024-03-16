cmake_minimum_required(VERSION 3.0)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(HelloWorld)

file(GLOB_RECURSE SRC_FILES "src/*.cpp")
add_executable(hello main.cpp ${SRC_FILES})
target_include_directories(hello PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include")




set(SFML_DIR "/home/steve/skds/SFML-2.6.1/lib/cmake/SFML")
find_package(SFML 2.6 REQUIRED network audio graphics window system)
target_include_directories(hello PUBLIC ${SFML_INCLUDE_DIR})
# target_link_libraries(hello ${SFML_LIBRARIES} ${SFML_DEPENDENCIES})
target_link_libraries(hello sfml-graphics sfml-window sfml-system sfml-audio sfml-network)

