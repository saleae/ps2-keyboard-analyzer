cmake_minimum_required (VERSION 3.11)
project(ps2_keyboard_analyzer)

add_definitions( -DLOGIC2 )

# enable generation of compile_commands.json, helpful for IDEs to locate include files.
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# custom CMake Modules are located in the cmake directory.
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(ExternalAnalyzerSDK)

set(SOURCES 
src/PS2KeyboardAnalyzer.cpp
src/PS2KeyboardAnalyzer.h
src/PS2KeyboardAnalyzerResults.cpp
src/PS2KeyboardAnalyzerResults.h
src/PS2KeyboardAnalyzerScanCodes.h
src/PS2KeyboardAnalyzerSettings.cpp
src/PS2KeyboardAnalyzerSettings.h
src/PS2KeyboardSimulationDataGenerator.cpp
src/PS2KeyboardSimulationDataGenerator.h
)

add_analyzer_plugin(ps2_keyboard_analyzer SOURCES ${SOURCES})
