cmake_minimum_required(VERSION 3.13)

project(rte_misc)

# Include ov core (if it isn't already included)
find_package(RTE)

# Include ov helper functions and definitions
get_target_property(RTE_CMAKE_DIR ov RTE_CMAKE_DIR)
include(${RTE_CMAKE_DIR}/ov_functions.cmake)
include(${RTE_CMAKE_DIR}/ov_definitions.cmake)

# Add message system library
add_subdirectory(MessageSys)


# Export all targets to make build tree importable via find_package(RTEfblib)
 export(EXPORT ${PROJECT_NAME}
     FILE RTEMiscConfig.cmake)
