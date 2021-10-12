add_library (utilitiesLib STATIC
	CmdlineUtil.h CmdlineUtilWin.cpp
	)

target_include_directories (utilitiesLib
	PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
	)

target_link_libraries (utilitiesLib PRIVATE
	)
