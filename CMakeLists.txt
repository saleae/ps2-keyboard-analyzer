cmake_minimum_required (VERSION 3.11)
project(ps2_keyboard_analyzer)

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
