
#project(fronend)


 

#############################################
#               Build fronend.exe           #
#############################################

file(GLOB_RECURSE SRC_FRONTEND ${CMAKE_SOURCE_DIR}/frontend/*.cpp)
include_directories(${CMAKE_SOURCE_DIR}/frontend/)

add_executable(frontend.exe ${SRC_FRONTEND})

target_link_libraries(frontend.exe com-psi)
target_link_libraries(frontend.exe aby3-ML)
target_link_libraries(frontend.exe com-psi_Tests)
target_link_libraries(frontend.exe aby3_Tests)


find_library(
    tests_cryptoTools_LIB
    NAMES tests_cryptoTools
    HINTS "${libOTe_Dirs}/lib/")

target_link_libraries(frontend.exe ${tests_cryptoTools_LIB})
