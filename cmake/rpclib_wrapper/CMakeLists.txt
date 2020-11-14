cmake_minimum_required(VERSION 3.5.0)
project(rpclib_wrapper)

LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/../cmake-modules") 
INCLUDE("${CMAKE_CURRENT_LIST_DIR}/../cmake-modules/CommonSetup.cmake")
CommonSetup()

IF(UNIX)
    set(RPC_LIB_DEFINES " -D MSGPACK_PP_VARIADICS_MSVC=0")
    set(CMAKE_CXX_FLAGS "${RPC_LIB_DEFINES} ${CMAKE_CXX_FLAGS}")    
ENDIF()

add_subdirectory("${AIRSIM_ROOT}/AirLib/deps/rpclib" "${CMAKE_CURRENT_BINARY_DIR}/rpclib")

set_target_properties(rpc
    PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${AIRSIM_ROOT}/AirLib/deps/rpclib/lib/x64"
    LIBRARY_OUTPUT_DIRECTORY "${AIRSIM_ROOT}/AirLib/deps/rpclib/lib/x64"
)

