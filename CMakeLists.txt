cmake_minimum_required(VERSION 3.10)
project(raisim VERSION 0.6.0 LANGUAGES CXX)

# Include CMake helper modules
include(GNUInstallDirs)

# Build options
option(RAISIM_EXAMPLE "Build example applications." FALSE)

#==
# Package installation
#==
install(
        DIRECTORY
        ${CMAKE_CURRENT_LIST_DIR}/include
        DESTINATION
        ${CMAKE_INSTALL_PREFIX}
)

install(
        DIRECTORY
        "${CMAKE_CURRENT_LIST_DIR}/lib"
        DESTINATION
        ${CMAKE_INSTALL_PREFIX}
)

#==
# Examples
#==
if(RAISIM_EXAMPLE)
    list(APPEND CMAKE_PREFIX_PATH ${CMAKE_CURRENT_SOURCE_DIR})
    add_subdirectory(examples)
endif()

# EOF
