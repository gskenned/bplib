##################################################################
#
# Bundle Protocol Library (BPLib) CMake build recipe
#
# This is for the "file_offload" stub functions
#
##################################################################

add_library(bplib_file_offload_stubs STATIC
    bplib_file_offload_stubs.c
)

target_include_directories(bplib_file_offload_stubs PUBLIC
    $<TARGET_PROPERTY:bplib_file_offload,INTERFACE_INCLUDE_DIRECTORIES>
)

target_link_libraries(bplib_file_offload_stubs PUBLIC
  ut_assert
)
