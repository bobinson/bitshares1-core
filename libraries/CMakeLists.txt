
cmake_minimum_required(VERSION 3.10)


SET (BOOST_ROOT "/home/bkb/src/boost/boost_1_56_0")
SET (BOOST_INCLUDEDIR "${BOOST_ROOT}/include")
SET (BOOST_LIBRARYDIR "${BOOST_ROOT}/lib")

SET (BOOST_MIN_VERSION "1.50.0")
set (Boost_NO_BOOST_CMAKE ON)
FIND_PACKAGE(Boost ${BOOST_MIN_VERSION} REQUIRED)
if (NOT Boost_FOUND)
    message(FATAL_ERROR "Fatal error: Boost (version >= 1.56) required.")
else()
    message(STATUS "Setting up BOOST")
    message(STATUS " Includes - ${Boost_INCLUDE_DIRS}")
    message(STATUS " Library  - ${Boost_LIBRARY_DIRS}")
    include_directories(${Boost_INCLUDE_DIRS})
    link_directories(${Boost_LIBRARY_DIRS})
endif (NOT Boost_FOUND)


add_subdirectory( db )
add_subdirectory( blockchain )
