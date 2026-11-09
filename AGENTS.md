# Agent instructions

This repository owns pma120 board configuration, peripherals, firmware
selection, partition layout, power policy, and packaging. Shared SM8850
resources and operations belong to `UniXNU-sm8850-common`. The documentation
site, component catalog, and common build tools belong to `UniXNU`.

Read these UniXNU pages before editing:

1. [Porting](https://unixnu.com/porting/)
2. [Device repositories](https://unixnu.com/porting/device-repository)
3. [Components](https://unixnu.com/reference/components)
4. [Device trees](https://unixnu.com/porting/device-tree)
5. [UEFI firmware](https://unixnu.com/porting/uefi-firmware)

Hardware facts for this board (GIC bases, CPU topology, memory reservations,
panel) are recorded in `X9U-iOS移植/设备情报.md`; verify against the phone's
own device tree (`device/PMA120/fdt.dtb`) before committing.

Run from the UniXNU checkout:

```sh
./unixnu defconfig pma120_ipados27_defconfig -D ../UniXNU-pma120
./unixnu status --json -D ../UniXNU-pma120
./unixnu tree -D ../UniXNU-pma120
./unixnu build kernel -D ../UniXNU-pma120
```

Report commands, outputs, missing inputs, and hardware observations
separately. Update the porting record as implementation proceeds. Write
concise English.
