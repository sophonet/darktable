include_directories(${CMAKE_CURRENT_SOURCE_DIR}/..)
include_directories(${CMAKE_CURRENT_BINARY_DIR}/..)
add_executable(darktable-cltest main.c)

set_target_properties(darktable-cltest PROPERTIES LINKER_LANGUAGE C)
target_link_libraries(darktable-cltest lib_darktable)

if (WIN32)
  _detach_debuginfo (darktable-cltest bin)
endif(WIN32)

install(TARGETS darktable-cltest DESTINATION ${CMAKE_INSTALL_BINDIR} COMPONENT DTApplication)
