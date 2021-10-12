# utilities test

cmake_minimum_required (VERSION 3.20)
project ("utilitiesTest")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package (GTest CONFIG REQUIRED)
find_package (RapidJSON CONFIG REQUIRED)
#add_subdirectory (../src ${CMAKE_CURRENT_BINARY_DIR}/lib)
add_subdirectory (${CMAKE_CURRENT_SOURCE_DIR}/../src ${CMAKE_CURRENT_BINARY_DIR}/lib)

add_executable (utilitiesTest
	JActiveQueue_test.cpp
	JBuffer_test.cpp
	JExp_test.cpp
	...
	JTime_test.cpp
	JTimer_test.cpp
	JWaitCond_test.cpp
	OptionUtil_test.cpp
	test_main.cpp)


target_link_libraries (utilitiesTest
	PRIVATE utilitiesLib
	#PRIVATE ${CMAKE_CURRENT_BINARY_DIR}/lib/utilitiesLib.lib
	PRIVATE GTest::gtest GTest::gtest_main)
