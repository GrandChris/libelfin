#
# \file       CMakeLists.txt
# \author     GrandChris
# \date       2020-10-11
# \brief      Build the library
#

cmake_minimum_required(VERSION 3.16)

# Create the project
project(libelfin VERSION 1.0 LANGUAGES CXX)


############################################################################
# dwarf

# Add executable
add_library(dwarf)

target_include_directories(dwarf PUBLIC "./")

# Add source files
file(GLOB DWARF_SOURCE CONFIGURE_DEPENDS
  "./dwarf/*.cc"
)

target_sources(dwarf PRIVATE ${DWARF_SOURCE})


############################################################################
# elf

# Add executable
add_library(elf)

# Include directories
target_include_directories(elf PUBLIC "./")

# Add source files
file(GLOB ELF_SOURCE CONFIGURE_DEPENDS
  "./elf/*.cc"
)

target_sources(elf PUBLIC ${ELF_SOURCE})

