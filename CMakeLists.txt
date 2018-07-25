cmake_minimum_required (VERSION 3.10.2)
project (KDE)

# Bring header files into build
include_directories(include)

# Bring source files with wildcard pattern
file(GLOB MATH_SOURCES "src/math/*.cpp")
file(GLOB SOURCES "src/*.cpp")

# Build shared library
add_library(math SHARED ${MATH_SOURCES})

# Shared library
# set(PROJECT_LINK_LIBS math.so)
# link_directories(~/Code/kde/spike/cmake/build)

# Build executable
add_executable(main ${SOURCES})
target_link_libraries(main math)

# Set installation directory
install(TARGETS math DESTINATION /usr/lib)
