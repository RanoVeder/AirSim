cmake_minimum_required(VERSION 3.5.0)
project(AirSim)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory("rpclib_wrapper")
add_subdirectory("AirLib")
add_subdirectory("MavLinkCom")
add_subdirectory("AirLibUnitTests")
add_subdirectory("HelloDrone")
add_subdirectory("HelloCar")
add_subdirectory("DroneShell")
add_subdirectory("DroneServer")



        # REM //---------- copy binaries and include for MavLinkCom in deps ----------
        # set MAVLINK_TARGET_LIB=AirLib\deps\MavLinkCom\lib
        # if NOT exist %MAVLINK_TARGET_LIB% mkdir %MAVLINK_TARGET_LIB%
        # set MAVLINK_TARGET_INCLUDE=AirLib\deps\MavLinkCom\include
        # if NOT exist %MAVLINK_TARGET_INCLUDE% mkdir %MAVLINK_TARGET_INCLUDE%
        # robocopy /MIR MavLinkCom\include %MAVLINK_TARGET_INCLUDE%
        # robocopy /MIR MavLinkCom\lib %MAVLINK_TARGET_LIB%
        
        # REM //---------- all our output goes to Unreal/Plugin folder ----------
        # if NOT exist Unreal\Plugins\AirSim\Source\AirLib mkdir Unreal\Plugins\AirSim\Source\AirLib
        # robocopy /MIR AirLib Unreal\Plugins\AirSim\Source\AirLib  /XD temp *. /njh /njs /ndl /np
        # copy /y AirSim.props Unreal\Plugins\AirSim\Source\AirLib
        