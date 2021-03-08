cmake_minimum_required(VERSION 3.5)
# Simplified CMakeLists.txt to simplify inclusion from parent fw project
#project(parson C)

include (GNUInstallDirs)

set(PARSON_VERSION 1.1.0)
add_library(parson OBJECT parson.c)
target_include_directories(parson INTERFACE $<INSTALL_INTERFACE:include>)

set_target_properties(parson PROPERTIES PUBLIC_HEADER "parson.h")
set_target_properties(parson PROPERTIES VERSION ${PARSON_VERSION})
set_target_properties(parson PROPERTIES SOVERSION ${PARSON_VERSION})

#install(
#    TARGETS parson
#    EXPORT parsonTargets
#    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR} COMPONENT shlib
#    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
#    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
#    PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
#)
#
#install(
#    EXPORT parsonTargets
#    FILE parsonConfig.cmake
#    NAMESPACE parson::
#    DESTINATION ${CMAKE_INSTALL_LIBDIR}/cmake/${PROJECT_NAME}
#)

