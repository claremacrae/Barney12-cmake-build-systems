add_executable (utilitiesTest
	CmdlineUtil_test.cpp
	test_main.cpp
	)

target_link_libraries (utilitiesTest
	PRIVATE utilities::utilitiesLib
)
