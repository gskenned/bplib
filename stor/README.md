README for stor folder

Storage (STOR) APIs

Bundle Cache (BC) bundle-cache

|API|Description|
|:- |:- |
int BPL_BC_configure (int key, bplib_cache_module_valtype_t vt, const void *val)|Configure Bundle Cache
int BPL_BC_query (int key, bplib_cache_module_valtype_t vt, const void **val)|Query Bundle Cache telemetry
int BPL_BC_start ()|Start Bundle Cache if stopped
int BPL_BC_stop ()|Stop Bundle Cache if started

Persistent Storage (store) store

|API|Description|
|:- |:- |
int BPL_file_offload_instantiate|Create File Offload Instance
int BPL_file_offload_configure|Configure
int BPL_file_offload_scan|Restore all stored bundles (after restart)
int BPL_file_offload_query|Get HK data
int BPL_file_offload_start|Create base folder|mkdir|OS_mkdir|
int BPL_file_offload_stop|Noop

Queue Manager (QM) queue-manager
