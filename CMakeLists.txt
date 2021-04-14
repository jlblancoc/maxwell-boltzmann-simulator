# ---------------------------------------------------------------------------
#           Maxwell-Boltzmann distribution demonstration (2D/3D)
#   Copyright (C) 2012  Jose Luis Blanco
# ---------------------------------------------------------------------------
cmake_minimum_required(VERSION 3.0)

project(maxwell_boltzmann)

find_package(mrpt-gui REQUIRED)
find_package(mrpt-math REQUIRED)

# Set optimized building:
if(CMAKE_COMPILER_IS_GNUCXX AND NOT CMAKE_BUILD_TYPE MATCHES "Debug")
	SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3 -mtune=native")
endif()

# Declare the target (an executable)
add_executable(boltz-3d maxwell-boltzmann.cpp)
target_link_libraries(boltz-3d mrpt::gui mrpt::math)

# Declare the target (an executable)
add_executable(boltz-2d maxwell-boltzmann.cpp)
target_link_libraries(boltz-2d mrpt::gui mrpt::math)

target_compile_definitions(boltz-2d PRIVATE "SIMUL_2D")
