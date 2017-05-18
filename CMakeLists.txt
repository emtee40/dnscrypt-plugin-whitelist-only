cmake_minimum_required(VERSION 2.8)

project(whitelist C)

set(WHITELIST_MAJOR_VERSION 0)
set(WHITELIST_MINOR_VERSION 1)
set(WHITELIST_VERSION ${WHITELIST_MAJOR_VERSION}.${WHITELIST_MINOR_VERSION})

set(INSTALL_LIB_DIR lib/dnscrypt-proxy CACHE PATH "Installation directory for libraries")

IF(NOT CMAKE_BUILD_TYPE)
  SET(CMAKE_BUILD_TYPE Release CACHE STRING "Choose the type of build, options are: None Debug Release RelWithDebInfo MinSizeRel." FORCE)
ENDIF(NOT CMAKE_BUILD_TYPE)

find_library(LDNS_LIBRARY NAMES ldns libldns)

add_library(whitelist SHARED whitelist.c fpst.c fpst.h)

target_link_libraries(whitelist ldns)

install(TARGETS whitelist DESTINATION ${INSTALL_LIB_DIR})
