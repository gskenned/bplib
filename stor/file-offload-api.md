---
output:
    word_document
---
**Persistent Storage (file_offload) bplib/stor/store/file_offload.c**

|File Offload API|Description|
|:- |:- |
`static BPL_file_offload_svc_t *bplib_file_offload_instantiate(BPL_file_offload_state_t parent, void *init_arg);`|Create a file offload service and return a pointer to the service
`static int BPL_offload_configure(BPL_file_offload_svc_t *svc, int key, BPL_cache_module_valtype_t vt, const void *val)`|Configure a file offload service. The only configuration option is to set the name of the base directory. key must be bplib_cache_confkey_offload_base_dir. vt - value type is ignored and assumed to be bplib_cache_module_valtype_string. val is a null-terminated string containing the base directory name.
`static int BPL_offload_query(BPL_file_offload_svc_t *svc, int key, BPL_cache_module_valtype_t vt, const void **val)`|Query and return housekeeping data. 
`static int BPL_offload_start(BPL_file_offload_svc_t *svc)`|Start a file offload service.
`static int BPL_offload_stop(BPL_file_offload_svc_t *svc)`|Stop a file offload service.
`static int BPL_offload_offload(BPL_file_offload_svc_t *svc, bp_sid_t *sid, BPL_file_offload_pblk_t *pblk)`|Offload a bundle to a file. sid is the Storage ID for the bundle. pblk is a pointer to the bundle Primary Block.
`static int BPL_offload_restore(BPL_file_offload_svc_t *svc, bp_sid_t sid, BPL_file_offload_pblk_t **pblk_out)`|Restore a bundle from a file. sid is the Storage ID of the bundle. pblk_out returns the restored bundle.
`static int BPL_offload_delete(BPL_file_offload_svc_t *svc, bp_sid_t sid)`|Delete a bundle from persistent storage by Storage ID.
`static int BPL_file_offload_scan(BPL_file_offload_svc_t *svc, BPLIB_cache_module_valtype_t vt, const void **val)`|Scans persistent storage for stored bundles. Returns an iterable list of bundles in "val". vt is a data structure type for an iterable list of bundles.

**Based on file_offload.c bplib/store/file_offload.c**

```
static bplib_mpool_block_t *bplib_file_offload_instantiate(bplib_mpool_ref_t parent, void *init_arg);
static int bplib_file_offload_configure(bplib_mpool_block_t *svc, int key, bplib_cache_module_valtype_t vt, const void *val);
static int bplib_file_offload_query(bplib_mpool_block_t *svc, int key, bplib_cache_module_valtype_t vt, const void **val);
static int bplib_file_offload_start(bplib_mpool_block_t *svc);
static int bplib_file_offload_stop(bplib_mpool_block_t *svc);
static int bplib_file_offload_offload(bplib_mpool_block_t *svc, bp_sid_t *sid, bplib_mpool_block_t *pblk);
static int bplib_file_offload_restore(bplib_mpool_block_t *svc, bp_sid_t sid, bplib_mpool_block_t **pblk_out);
static int bplib_file_offload_release(bplib_mpool_block_t *svc, bp_sid_t sid);
```
