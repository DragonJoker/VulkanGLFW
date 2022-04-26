cmake_minimum_required(VERSION 3.0.0)

set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

project(vulkan VERSION 0.1.0)

include(CTest)
enable_testing()

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(vulkan main.cpp)

find_package(Vulkan REQUIRED)
find_package(glfw REQUIRED)
find_package(glm REQUIRED)
target_link_libraries(vulkan PUBLIC Vulkan::Vulkan)
target_link_libraries(vulkan PUBLIC glfw::glfw)
target_link_libraries(vulkan PUBLIC glm::glm)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
