# Test Environment

-   PC: Aurora
-   Operating system: Windows 11 Pro
-   CPU: AMD Ryzen 7 7800X3D
-   GPU: NVIDIA GeForce RTX 5070
-   RAM: 32 GB G.SKILL Trident Z5 Neo RGB DDR5-6000 CL30
-   Emulator: Xenia Canary, primary known-good Project X-360 build
-   Controller baseline: `hid = "any"`
-   Storage baseline: storage selection dialog enabled; Dummy HDD used
    when required
-   Audio baseline: `xma_decoder = "old"`
-   Graphics baseline: `readback_resolve = "full"`

Before submitting an official compatibility report, copy the exact Xenia
commit/build identifier from the tested executable/log into the issue
and attach a fresh `xenia.log` from the reproduced test.
