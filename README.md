# Huawei Solar HEMS

Home Assistent (HA) **Home Energy Management System** (HEMS)

[![License][license-shield]](LICENSE) [![GitHub Last Commit][last-commit-shield]][commits] ![GitHub Stars][stars-shield] ![GitHub Watchers][watchers-shield] ![GitHub Forks][forks-shield]

[![Community Forum][forum-shield]][forum]

**Huawei Solar HEMS** assist you with **a set of custom** HA **template sensors**, **automations** and **dashboards** also referred to as the *"Huawei Solar HEMS package"*.

| Dashboard: Level 1                     |
|:--------------------------------------:|
| ![Dashboard-1](assets/dashboard-1.png) |

These custom sensors and automations calculate all the power and energy flows of your Huawei FusionSolar PV installation based on the sensors, services and information provided by [Huawei Solar Integration](https://github.com/wlcrs/huawei_solar), because this custom HA integration ONLY exposes the information and functions made available by Huawei Solar inverters directly via one of its Modbus interfaces, which is far away from enhanced requirements of an HEMS.

All custom template sensors and automations are available as HA package files and all dashboards are available through HA YAML dashboards for an easy [Installation](#installation).
For an overview and a more detailed description of the custom sensors and automations, please refer to the [Huawei Solar HEMS Wiki Pages](https://github.com/heinemannj/huawei_solar_hems/wiki).

## Table of Contents

- [Additional HEMS features](#additional-hems-features)
  - [Forecasting](#forecasting)
  - [Monitoring](#monitoring)
  - [Tibber prices](#tibber-prices)
  - [Tibber consumption and costs](#tibber-consumption-and-costs)
- [Installation](#installation)
- [System setup](#system-setup)
  - [House load](#house-load)
  - [FusionSolar PV](#fusionsolar-pv)
- [FAQ - Troubleshooting](#faq---troubleshooting)

## Additional HEMS features

### Forecasting

| Dashboard: Level 2                     |
|:--------------------------------------:|
| ![Dashboard-2](assets/dashboard-2.png) |

- **PV Solar forecasts** by the usage of [Solcast integration](https://github.com/BJReplay/ha-solcast-solar)
  <br>This custom component integrates the [Solcast Hobby PV Forecast API](https://solcast.com/free-rooftop-solar-forecasting) into HA.
- **EPEX Spot electricity price forecasts** by the usage of [EPEXSpot integration](https://github.com/mampfes/ha_epex_spot)
  <br>This custom component adds electricity prices from the European Power EXchange ( [EPEX Spot](https://www.epexspot.com/en/about) ) into HA.
  <br>It covers Austria, Belgium, Denmark, Germany, Finland, France, Luxembourg, the Netherlands, Norway, Poland, Sweden, the United Kingdom and Switzerland at this time.
- **Hourly Weather forecasts**
- **House load and batteries SOC forecasts** by the usage of the [EMHASS Add-on](https://github.com/davidusb-geek/emhass-add-on)
  <br>[EMHASS](https://github.com/davidusb-geek/emhass) (Energy Management for Home Assistant) is an optimization tool designed for residential households connected to HA.

### Monitoring

| Dashboard: Level 3                     |
|:--------------------------------------:|
| ![Dashboard-3](assets/dashboard-3.png) |
  
### Tibber prices

| Dashboard: Level 4-1 - Today & tomorrow        | Dashboard: Level 4-2 - Past                    |
|:----------------------------------------------:|:----------------------------------------------:|
| ![Dashboard-4-1](assets/dashboard-4-1.png)     | ![Dashboard-4-2](assets/dashboard-4-2.png)     |

### Tibber consumption and costs

| Dashboard: Level 4-3-1 - Hourly                | Dashboard: Level 4-3-2 - Daily                 |
|:----------------------------------------------:|:----------------------------------------------:|
| ![Dashboard-4-3-1](assets/dashboard-4-3-1.png) | ![Dashboard-4-3-2](assets/dashboard-4-3-2.png) |

| Dashboard: Level 4-3-3 - Monthly               | Dashboard: Level 4-3-4 - Yearly                |
|:----------------------------------------------:|:----------------------------------------------:|
| ![Dashboard-4-3-3](assets/dashboard-4-3-3.png) | ![Dashboard-4-3-4](assets/dashboard-4-3-4.png) |

## Installation

For [installation](https://github.com/heinemannj/huawei_solar_hems/wiki/Installation) follow all [prerequisites and installation guides](https://github.com/heinemannj/huawei_solar_hems/wiki/Installation#prerequisites) strictly!

* **Step by step**.

## System setup

### House load

|||
|:---|:---:|
|**Power distribution**|<img src="assets/em-power-flows.png" width=400>|
|- Back-up fuses<br>- Surge protection<br>- Residual Current Devices (RCD)<br>- Circuit breaker|<img src="assets/em-meter-cabinet.png" width=400>|
|**Energy measurement**|<img src="assets/em-energy-flows.png" width=400>|
|- Smart meter<br>&#160;&#160;<sup>HUAWEI Smart Power Sensor DTSU666-H 100A/50mA|<img src="assets/em-smart-meter.png" width=400>|
|- Tibber Pulse|<img src="assets/em-tibber-pulse.png" width=400>|
|- Three-phase energy meters<br>&#160;&#160;<sup>Shelly Pro 3EM - 120A|<img src="assets/em-shelly-pro-3em.png" width=400>|

### FusionSolar PV

The provided custom sensors are based on a setup with **one** Huawei Smart Energy Controller (**Inverter**) and **multiple** Huawei Smart String ESS (**Batteries**):

<img src="assets/em-system-setup.png">

- Inverter Type: SUN2000-6KTL-M1 (High Current)
- Inverter Firmware version: V100R001C00SPC165
- MBUS Firmware version: V100R001C00SPC335
- PV1: 3900 Wp
- PV2: 3900 Wp
- sDongle Type: sDongleA-05 (WiFi / Ethernet)
- sDongle Connectivitiy: Ethernet
- sDongle Firmware: V200R022C10SPC118
- Power meter present: three phase
- Optimizers Present: No
- Battery-1: LUNA2000-5KW-C0
- Battery-2: LUNA2000-10KW-C0
- Batteries Firmware version: V100R002C00SPC624
- Connect to the inverter: Via the `SUN200-<serial_no> WiFi`

This is reflected throughout this README and the [Huawei Solar HEMS Wiki Pages](https://github.com/heinemannj/huawei_solar_hems/wiki).

## Notes

* Alpha version at this stage.
  * Especially the persistant template sensors and all automations should be validated by the community.
  * Not for HA beginners, but hopefully our **community will help** ...
* In my environment [Wife Acceptance Factor](https://en.wikipedia.org/wiki/Wife_acceptance_factor) (WAF) is strongly increasing - **Save your money to have more fun** ;-)
* **Save our earth** and **protect** next generations of **our children**!
* **Think long term** and **do the needful**.

Already opened Discussion: [Huawei Solar Discussion > Dashboard #355](https://github.com/wlcrs/huawei_solar/discussions/355)

- Private information is stored in secrets.yaml (not uploaded).

---

## FAQ - Troubleshooting

**At this time just a copy of** [Huawei Solar FAQ](https://github.com/wlcrs/huawei_solar#faq---troubleshooting).
<br>**To be adjusted in short time** ;-)

---

**Q**: Why do I get the error "Connection succeeded, but failed to read from inverter." while setting up this integration?

**A**: While the integration was able to setup the initial connection to the Huawei Inverter, it did not respond to any queries in time. This is either caused by using an invalid slave ID (typically 0 or 1, try both or ask your installer if unsure), or because an other device established a connection with the inverter, causing the integration to lose it's connection

---

**Q**: Will the FusionSolar App still work when using this integration?

**A**: The inverter will still send it's data to the Huawei cloud, and you will still be able to see live statistics from your installation in the FusionSolar App. However, if you are using this integration via the network, and you (or your installer) need to use the 'Device commissioning' feature of the app, you will need to disable this integration.

---

<a name="daily-yield"></a>

**Q**: The "Daily Yield" value reported does not match with the value from FusionSolar?

**A**: The "Daily Yield" reported by the inverter is the *output* yield of the inverter, and not the *input* from your solar panels. It therefore includes the yield from discharging the battery, but misses the yield used to charge the battery. FusionSolar computes the "Yield" by combining the values from "Daily Yield", "Battery Day Charge" and "Battery Day Discharge". [More information on the Wiki ...](https://github.com/wlcrs/huawei_solar/wiki/Daily-Solar-Yield)

---

<a name="debugging"></a>

**Q**: I can't get this integration to work. What am I doing wrong?

**A**: First make sure that ['Modbus TCP' access is enabled in the settings of your inverter](https://forum.huawei.com/enterprise/en/modbus-tcp-guide/thread/789585-100027). Next, check if the port is correct. Some inverters use port 6607 instead of 502 (this can change for you after a firmware update!). If that doesn't work for you, and you intend to write an issue, make sure you have the relevant logs included. For this integration, you can enable all relevant logs by including the following lines in your `configuration.yaml`:

```yaml
logger:
  logs:
    pymodbus: debug # only include this if you're having connectivity issues
    huawei_solar: debug
    homeassistant.components.huawei_solar: debug
```
By providing logs directly when creating the issue, you will likely get help much faster.

[commits-shield]: https://img.shields.io/github/commit-activity/y/heinemannj/huawei_solar_hems.svg
[commits]: https://github.com/heinemannj/huawei_solar_hems/commits/master
[actions-shield]: https://github.com/heinemannj/huawei_solar_hems/workflows/Home%20Assistant%20CI/badge.svg
[actions]: https://github.com/heinemannj/huawei_solar_hems/actions
[contributors]: https://github.com/heinemannj/huawei_solar_hems/graphs/contributors
[discord-shield]: https://img.shields.io/discord/330944238910963714.svg
[discord]: https://discord.gg/c5DvZ4e
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg
[forum]: https://community.home-assistant.io/?u=heinemannj
[heinemannj]: https://github.com/heinemannj
[travis-shield]: https://travis-ci.org/heinemannj/huawei_solar_hems.svg?branch=master
[travis]: https://travis-ci.org/heinemannj/huawei_solar_hems
[home-assistant]: https://home-assistant.io
[issue]: https://github.com/heinemannj/huawei_solar_hems/issues
[license-shield]: https://img.shields.io/badge/license-MIT-green.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2023.svg
[last-commit-shield]: https://img.shields.io/github/last-commit/heinemannj/huawei_solar_hems.svg
[stars-shield]: https://img.shields.io/github/stars/heinemannj/huawei_solar_hems.svg?style=social&label=Stars
[forks-shield]: https://img.shields.io/github/forks/heinemannj/huawei_solar_hems.svg?style=social&label=Forks
[watchers-shield]: https://img.shields.io/github/watchers/heinemannj/huawei_solar_hems.svg?style=social&label=Watchers
[black-duck-shield]: https://copilot.blackducksoftware.com/github/repos/heinemannj/huawei_solar_hems/branches/master/badge-risk.svg
[black-duck]: https://copilot.blackducksoftware.com/github/repos/heinemannj/huawei_solar_hems/branches/master/
