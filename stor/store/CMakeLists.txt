##################################################################
#
# Bundle Protocol Library (BPLib) CMake build recipe
#
# This is for the "file_offload" component.
#
##################################################################

add_library(bplib_file_offload OBJECT
    src/file_offload.c
)

target_include_directories(bplib_file_offload PRIVATE
    $<TARGET_PROPERTY:bplib_mpool,INTERFACE_INCLUDE_DIRECTORIES>
    $<TARGET_PROPERTY:bplib_v7,INTERFACE_INCLUDE_DIRECTORIES>
    $<TARGET_PROPERTY:bplib_cache,INTERFACE_INCLUDE_DIRECTORIES>
    $<TARGET_PROPERTY:bplib_common,INTERFACE_INCLUDE_DIRECTORIES>
)
target_include_directories(bplib_file_offload PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/inc
    $<TARGET_PROPERTY:bplib,INTERFACE_INCLUDE_DIRECTORIES>
    $<TARGET_PROPERTY:bplib_base,INTERFACE_INCLUDE_DIRECTORIES>
)

# Add unit test coverage subdirectory
if(BPLIB_ENABLE_UNIT_TESTS)
  add_subdirectory(ut-stubs)
  add_subdirectory(ut-coverage)
endif(BPLIB_ENABLE_UNIT_TESTS)
