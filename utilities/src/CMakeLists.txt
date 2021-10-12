add_library (utilitiesLib STATIC
	CmdlineUtil.h CmdlineUtilWin.cpp
	)
# Set up an ALIAS target (with :: in name)
# Dependent targets should use the utilities::utilitiesLib name...
# Then, if there is an error in the library name, users will
# find out at the point that CMake runs, rather than
# getting long, cryptic error messages at build time...
add_library(utilities::utilitiesLib ALIAS utilitiesLib)

target_include_directories (utilitiesLib
	PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
	)

target_link_libraries (utilitiesLib PRIVATE
	)
