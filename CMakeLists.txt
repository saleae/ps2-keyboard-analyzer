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

add_library(ps2_keyboard_analyzer SHARED ${SOURCES})
target_link_libraries(ps2_keyboard_analyzer PRIVATE Saleae::AnalyzerSDK)

if(MSVC)
    install(TARGETS ps2_keyboard_analyzer RUNTIME DESTINATION ".")
else()
    install(TARGETS ps2_keyboard_analyzer LIBRARY DESTINATION ".")
endif()

set_post_build_destination(ps2_keyboard_analyzer)
