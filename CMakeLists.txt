cmake_minimum_required(VERSION 2.8)
project(<project> CXX C)

set(CPACK_PACKAGE_VERSION_MAJOR "<major>")
set(CPACK_PACKAGE_VERSION_MINOR "<minor>")
set(CPACK_PACKAGE_VERSION_PATCH "<patch>")

set(APP_VERSION "${CPACK_PACKAGE_VERSION_MAJOR}.${CPACK_PACKAGE_VERSION_MINOR}.${CPACK_PACKAGE_VERSION_PATCH}")
set(APP_ASSOCIATED_TAG "v${APP_VERSION}")

set(CMAKE_CXX_FLAGS "-Wall -std=c++0x")


#find_package(Boost REQUIRED COMPONENTS system regex)
#find_package(<package> REQUIRED)

#include_directories(${Boost_INCLUDE_DIRS})
#link_directories(${Boost_LIBRARY_DIRS})
#set(LIBS ${LIBS} ${Boost_LIBRARIES})


#Documentation
#find_package(Doxygen REQUIRED)
#if(DOXYGEN_FOUND)
#    configure_file(${CMAKE_CURRENT_SOURCE_DIR}/Doxyfile.in ${CMAKE_CURRENT_BINARY_DIR}/Doxyfile @ONLY)
#    add_custom_target(doc ${DOXYGEN_EXECUTABLE} ${CMAKE_CURRENT_BINARY_DIR}/Doxyfile WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR} COMMENT "Generating API documentation with Doxygen" VERBATIM)
#endif(DOXYGEN_FOUND)


#Add a library
#add_library(<lib> SHARED <source>)
#target_link_libraries(<lib> ${LIBS})
#set_target_properties(<lib> PROPERTIES VERSION ${APP_VERSION})

#Add an executable
#add_executable(<exec> <source>)
#target_link_libraries(<exec> ${LIBS})
#set_target_properties(<exec> PROPERTIES VERSION ${APP_VERSION})
