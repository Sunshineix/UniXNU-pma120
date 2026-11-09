# UniXNU-pma120

UniXNU device support for the **OPPO Find X9 Ultra** (pma120, Qualcomm SM8850 "canoe",
Snapdragon 8 Elite Gen 5). Work in progress — this is a skeleton; nothing builds or boots yet.

## Status (2026-11-07)

| Layer | State |
| --- | --- |
| Device tree (phone's own fdt) | extracted, hashed (`device/PMA120/fdt.dtb`) |
| SoC facts (GIC, CPU topology, memory map, panel) | recorded in `X9U-iOS移植/设备情报.md` |
| UEFI platform `pma120Pkg` (Mu-Silicium) | complete skeleton + vendor DXEs extracted (423 files, BuildId `BOOT.MXF.2.5.3-00199-KAANAPALI-1.131443.27`) |
| `board.toml` / defconfig / feeds | skeleton with TODO placeholders |
| SoC support (`UniXNU-sm8850-common`) | skeleton |

## Build (once skeletons are complete)

```sh
cd UniXNU
./unixnu defconfig pma120_ipados27_defconfig -D ../UniXNU-pma120
./unixnu fetch -D ../UniXNU-pma120
./unixnu status --json -D ../UniXNU-pma120
./unixnu build kernel -D ../UniXNU-pma120
```

Firmware and payload inputs are recorded in `proprietary-files.txt`;
UEFI build and `fastboot boot` bring-up: `X9U-iOS移植/UEFI构建runbook.md`.

## References

- [Porting](https://unixnu.com/porting/) · [Device repositories](https://unixnu.com/porting/device-repository)
- [sheng port (SM8550 reference)](https://github.com/UniXNU/UniXNU-sheng)
- Project workspace: `X9U-iOS移植/` (立项文档, 设备情报, UEFI 方案与 runbook)
