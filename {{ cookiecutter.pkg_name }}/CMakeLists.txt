# ============================================================================ #
# CMake Initialisation
# ============================================================================ #
cmake_minimum_required(VERSION 3.5.1)
project({{cookiecutter.pkg_name}} VERSION 0.1.0 LANGUAGES C CXX)

# ============================================================================ #
# CMake Scripts Location & Misc config
# ============================================================================ #

# ============================================================================ #
# Project dependencies
# ============================================================================ #

find_package(catkin REQUIRED
             COMPONENTS roscpp
             # a_pkg
)

# ============================================================================ #
# Messages, Services, Actions
# ============================================================================ #

# ============================================================================ #
# List of sources
# ============================================================================ #
set(HEADERS)
set(SOURCES)

# ============================================================================ #
# Libraries, Executables, catkin_package
# ============================================================================ #

catkin_package(INCLUDE_DIRS include
               CATKIN_DEPENDS roscpp
                              #a_pkg
)

include_directories(include ${catkin_INCLUDE_DIRS})

# ============================================================================ #
# Installation
# ============================================================================ #
install(DIRECTORY launch
                  scripts
                  rqt
                  rviz
        DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
        )
install(DIRECTORY include/${PROJECT_NAME}
        DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
        )
