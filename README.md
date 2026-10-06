# firmware-lenovo-tb321fu

Proprietary firmware needed to run Linux ([armada-tb321fu](https://github.com/enij90/armada-tb321fu))
on the **Lenovo Legion Tab Gen 3 / Legion Y700 (2025), model TB321FU** (Qualcomm SM8650).

The files are installed by the armada-tb321fu image build into `/usr/lib/firmware`.
They are kept here, separate from the OS sources, the same way postmarketOS ships
`nonfree-firmware` packages for other Lenovo tablets.

## Contents

| Path | What |
| --- | --- |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/adsp*` | Audio DSP (audio, battery, USB-C/UCSI) |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/cdsp*` | Compute DSP |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/ipa_fws*` | IPA |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/*.jsn` | Protection-domain maps |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/gen70900_zap.mbn` | Adreno 750 zap shader (device-signed) |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/vpu33_p4.mbn` | Video decoder (iris), device-signed |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/novatek_ts_boe_fw.bin` | Touch controller firmware, BOE panel |
| `usr/lib/firmware/qcom/sm8650/lenovo/tb321fu/aw882xx_acf.bin`, `usr/lib/firmware/aw882xx_acf.bin` | Awinic AW882xx speaker amplifier configuration |
| `usr/lib/firmware/qcom/sm8650/Lenovo-Y700-TB321FU-tplg.bin` | AudioReach topology |
| `usr/lib/firmware/updates/ath12k/WCN7850/hw2.0/{amss,board-2}.bin` | Wi-Fi (WCN7850) firmware and board data for this tablet |
| `usr/lib/firmware/haptic_ram.bin`, `usr/lib/firmware/haptic_click.bin` | Awinic AW86937 vibration motor waveforms (from GUF296's tb321fu-haptics-debs) |
| `usr/share/qcom/sm8650/Lenovo/tb321fu/` | Sensor core (SSC) configuration served to the ADSP by hexagonrpcd: vendor sensor JSON configs, `sns_reg.conf`, `socinfo` (from GUF296's tb321fu-sensor-debs). No calibration: each tablet's factory calibration is read from its own `persist` partition |

`SHA256SUMS` lists every file.

No per-device data is included. The speaker calibration (`aw_cali.bin`) and the sensor
registry with the factory calibrations are unique to each tablet and stay on its own
`persist` partition.

## Origin

Extracted from the Lenovo stock ROM (`TB321FU_ROW_OPEN_USER_Q00002.0_W_ZUI_17.5.10.319`) and
from the TB321FU Linux port by [GUF296](https://github.com/GUF296), whose work made this
port possible.

## License

These files are the property of Qualcomm Technologies, Inc., Lenovo and their suppliers.
They are redistributed only so that owners of this tablet can run Linux on it, as Armada,
ROCKNIX and postmarketOS do for other devices. No license is granted by this repository.
If you are a rights holder and want them removed, please open an issue and they will be
taken down.
