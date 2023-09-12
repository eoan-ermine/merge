cmake_minimum_required(VERSION 3.11)

project(merge CXX)
set(CMAKE_CXX_STANDARD 23)

find_package(Boost 1.74.0 REQUIRED COMPONENTS program_options)
if(Boost_FOUND)
  include_directories(${Boost_INCLUDE_DIRS})
endif()

include_directories(src)
add_executable(merge
	src/main.cpp
)
target_link_libraries(merge PRIVATE ${Boost_LIBRARIES})
