#Generated by VisualGDB project wizard.
#Note: VisualGDB will automatically update this file when you add new sources to the project.

cmake_minimum_required(VERSION 2.7)
project(ShariSync)
find_package(ICU REQUIRED COMPONENTS UC i18n)
set(LIBRARIES_FROM_REFERENCES -lwiringPi)
# Add the pugixml directory to the project
add_subdirectory(libs/pugixml-1.14)

add_executable(ShariSync ShariSync.h ShariSync.cpp compulink.h compulink.cpp jvc.h jvc.cpp vfd.h vfd.cpp libs/base64.hpp SPI.h SPI.cpp)
target_include_directories(ShariSync PRIVATE ${CMAKE_SYSROOT}/usr/local/include ${CMAKE_SYSROOT}/usr/include/linux/spi libs libs/pugixml-1.14/src ${ICU_INCLUDE_DIRS})
target_link_libraries(ShariSync PRIVATE ${LIBRARIES_FROM_REFERENCES} pugixml ${ICU_LIBRARIES})
