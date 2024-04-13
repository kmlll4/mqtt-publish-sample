PROJECT(PAHO_DEMO LANGUAGES CXX C)
cmake_minimum_required(VERSION 3.5)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread")

OPTION (WITH_SSL "Build With SSL" OFF)
# CONFIGURE_FILE (
#     "${PROJECT_SOURCE_DIR}/config.h.in"
#     "${PROJECT_SOURCE_DIR}/config.h")

add_executable(aaa main.cpp)

if(WITH_SSL)
target_link_libraries(aaa paho-mqtt3cs paho-mqttpp3)
else()
target_link_libraries(aaa paho-mqtt3c paho-mqttpp3)
endif()