cmake_minimum_required(VERSION 3.9...3.22 FATAL_ERROR)

#set(KWSYS_NAMESPACE mitksys)
set(KWSYS_USE_SystemTools 1)
set(KWSYS_USE_RegularExpression 1)
set(KWSYS_USE_Directory 1)
set(KWSYS_USE_Base64 1)
set(KWSYS_USE_MD5 1 )
set(KWSYS_USE_CommandLineArguments 1)
set(KWSYS_USE_Process 1)
set(KWSYS_USE_DynamicLoader 0)
set(KWSYS_USE_Glob 1)
set(KWSYS_USE_Registry 1)
set(KWSYS_USE_SystemInformation 1)
set(KWSYS_INSTALL_EXPORT_NAME kwsys)
set(KWSYS_INSTALL_LIB_DIR lib)
set(KWSYS_INSTALL_BIN_DIR bin)
set(KWSYS_INSTALL_INCLUDE_DIR include)
set(KWSYS_INSTALL_EXPORT_DIR export)
set(KWSYS_PROPERTIES_C WINDOWS_EXPORT_ALL_SYMBOLS FALSE)
set(CMAKE_INSTALL_PREFIX ${PROJECT_BINARY_DIR}/install)
set( _macosx_rpath 1)
if(DEFINED CMAKE_MACOSX_RPATH AND NOT "${CMAKE_MACOSX_RPATH}" STREQUAL "")
  set(_macosx_rpath ${CMAKE_MACOSX_RPATH})
endif()
set(KWSYS_PROPERTIES_CXX MACOSX_RPATH ${_macosx_rpath} WINDOWS_EXPORT_ALL_SYMBOLS FALSE)

add_subdirectory(kwsys)

#mitkMacroEmptyExternalProject(mitkKWSys)
#[[
mitk_create_module(
  FORCE_STATIC
  NO_INIT
)]]