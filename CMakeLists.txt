cmake_minimum_required(VERSION "3.16.5")

project("HelloWorld")

add_executable("${PROJECT_NAME}"  "HelloWorld.cpp")

install(TARGETS "${PROJECT_NAME}" DESTINATION bin)		#${CMAKE_INSTALL_PREFIX}/bin
install(FILES "HelloWorld.cpp"  DESTINATION src)		#${CMAKE_INSTALL_PREFIX}/src

include(CTEST)

add_test("test1" "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}")
add_test("test2" "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}" "some-parameter")
