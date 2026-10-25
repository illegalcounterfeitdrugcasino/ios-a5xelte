# STARLTE: Galaxy S9 (SM-G960F, Exynos 9810)

This branch adds `MACHINE_CONFIG=STARLTE` on top of the herolte (Galaxy S7)
port: `xnu/patches/0300-starlte-board-target.patch`. It reuses the HEROLTE
code with the S9 framebuffer (0xcc000000, 1440x2960), boot MPIDR 0 and a log
page at 0x91fff100, and compiles out the Exynos 8890 keys, touch, APM/PMIC,
GPU and fuel-gauge drivers, whose addresses are other hardware on the 9810.

The S9 loader, ADT generator and boot-image packer live in the separate
project-starbite workspace (shim/starlte, tools/mkadt_starlte.py,
tools/starlte-pack-boot.py). Run the `xnu` workflow (default STARLTE) to get
`kernel.development.starlte`.
