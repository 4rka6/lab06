cmake_minimum_required(VERSION 3.10)
project(solver)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(solver solver.cpp)

set(CPACK_PACKAGE_NAME "solver")
set(CPACK_PACKAGE_VERSION "1.0.0")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Quadratic equation solver")
set(CPACK_PACKAGE_VENDOR "4rka6")
set(CPACK_PACKAGE_CONTACT "4rka6@users.noreply.github.com")
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "4rka6")
set(CPACK_RPM_PACKAGE_LICENSE "MIT")

if(UNIX AND NOT APPLE)
    set(CPACK_GENERATOR "DEB;RPM")
elseif(WIN32)
    set(CPACK_GENERATOR "ZIP")
elseif(APPLE)
    set(CPACK_GENERATOR "DragNDrop")
endif()

include(CPack)
