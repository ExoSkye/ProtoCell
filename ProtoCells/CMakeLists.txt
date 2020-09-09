# CMakeList.txt : CMake project for ProtoCells, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

#Find Vulkan
include(FindVulkan)

if(Vulkan_FOUND)
	# Add source to this project's executable.
	add_executable (ProtoCells "ProtoCells.cpp" "ProtoCells.h")
	target_link_libraries(ProtoCells Vulkan::Vulkan glfw)
	target_include_directories(ProtoCells PUBLIC "../libs/glm/" PUBLIC "../libs/glfw/include" PUBLIC "../libs/CppConsole")
else()
	message(FATAL_ERROR "Can't find Vulkan")
endif()