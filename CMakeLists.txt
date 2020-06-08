cmake_minimum_required(VERSION 3.10)

project(NUOPC_DATA_MODELS LANGUAGES Fortran VERSION 0.1)
list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
message("CMAKE_MODULE_PATH is ${CMAKE_MODULE_PATH}")

find_package(MPI REQUIRED)
find_package(ESMF REQUIRED)

if(BLD_STANDALONE)
  add_subdirectory(share)
  list(APPEND EXTRA_LIBS share)
  list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/share")
endif()

add_subdirectory(streams)
add_subdirectory(dshr)

foreach(COMP datm dice dlnd docn drof dwav)
  if($COMP)
    add_subdirectory(COMP)
  endif()
endforeach(COMP)
