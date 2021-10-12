add_subdirectory (${CMAKE_CURRENT_SOURCE_DIR}/../src ${CMAKE_CURRENT_BINARY_DIR}/lib)

add_executable (utilitiesTest
	CmdlineUtil_test.cpp
	test_main.cpp
	)

target_link_libraries (utilitiesTest
	PRIVATE utilitiesLib
)
