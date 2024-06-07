README for stor folder

**Storage (STOR) APIs**

**Bundle Cache (BC) bplib/stor/bundle-cache**

|Bundle Cache API|Description|
|:- |:- |
int BPL_BC_configure (int key, bplib_cache_module_valtype_t vt, const void *val)|Configure Bundle Cache
int BPL_BC_query (int key, bplib_cache_module_valtype_t vt, const void **val)|Query Bundle Cache telemetry
int BPL_BC_start ()|Start Bundle Cache if stopped
int BPL_BC_stop ()|Stop Bundle Cache if started

**Persistent Storage (file_offload) bplib/stor/store/file_offload.c**

See [file-offload-api.md](file-offload-api.md).

**Queue Manager (QM) queue-manager**

No API
