# utilities lib

cmake_minimum_required (VERSION 3.20)
project ("utilitiesLib")
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package (OpenSSL REQUIRED)

add_library (utilitiesLib STATIC
	CmdlineUtil.h CmdlineUtilWin.cpp
	JActiveQueue.h JAlgoUtil.h JIntervalMap.h JQueue.h
	JAsyncTracker.h JAsyncTracker.cpp
	...
	OptionUtil.h OptionUtil.cpp
	WinUtil.h WinUtil.cpp)

if (WIN32)
	target_sources (utilitiesLib PUBLIC
		JFile.h JFile.cpp JFileImpl.h JFileImplWin.cpp
		JLog.h JLogWin.cpp
		...
		JWaitCond.h JWaitCondWin.cpp
		WinUtil.h WinUtil.cpp)
else()
	add_library (utilitiesLib STATIC
		JFile.h JFile.cpp JFileImpl.h JFileImpl.cpp
		JLog.h JLog.cpp
		...
		JWaitCond.h JWaitCond.cpp)
endif()

target_include_directories (utilitiesLib
	PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
	PRIVATE ${OPENSSL_INCLUDE_DIR})

target_link_libraries (utilitiesLib PRIVATE OpenSSL::SSL OpenSSL::Crypto)
