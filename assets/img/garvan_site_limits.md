![](https://images.contentstack.io/v3/assets/blt324fd0a04af716e6/blt3f0048229394c515/6405de96205f2b7a60b745d6/gimr-logo.png)
# Garvan: Site limits
This document collects all salient limits that you will be subjected to when using the on-site HPC.

**Source documents:**

https://intranet.gimr.garvan.org.au/display/DSP/HPC+Storage
## Wolfpack
### Storage limits
```shell

# Show the limits for the current working directory

pan_quota

# Show the limits for a scratch location

cd /share/ScratchGeneral
pan_quota
```
![Garvan Wolfpack: scratch space limits](garvan_wolfpack_site_limits_storage_1.png)

### Job size and time limits
**General user:** 100 cpu-cores, 1000 GB, TBD hours


### Interactive usage limits
**Default:** 1 cpu-core, 7.8 GB, 8 hours
