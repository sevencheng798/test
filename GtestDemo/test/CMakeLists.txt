#
# Creator 2019-05-07
#

add_executable(FirstMockTest FirstGmock.cpp)
#add_executable(SharedUniqueTestF SharedUnique2.cpp)
#add_executable(SharedConstructorTest SharedConstructor.cpp)

target_include_directories(FirstMockTest PUBLIC
	"${CMAKE_SOURCE_DIR}/common/include" 
	"${GTEST_INCLUDE_DIR}")

#target_include_directories(SharedUniqueTestF PUBLIC
#	"${CMAKE_SOURCE_DIR}/common/include" 
#	"${GTEST_INCLUDE_DIR}")

#target_include_directories(SharedConstructorTest PUBLIC
#	"${GTEST_INCLUDE_DIR}")

target_link_libraries(FirstMockTest gmock_main gmock gtest pthread)
#target_link_libraries(SharedUniqueTestF gtest_main gtest pthread)
#target_link_libraries(SharedConstructorTest gtest_main gtest pthread)

LIST(APPEND BINS FirstMockTest)
#LIST(APPEND BINS SharedUniqueTestF)
#LIST(APPEND BINS SharedConstructorTest)
cxx_install_multiple_bin("${BINS}")
