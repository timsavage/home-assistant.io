---
title: Combined Energy
description: Instructions on how to integrate Combined Energy Hub device sensors within Home Assistant.
ha_category:
  - Binary Sensor
  - Energy
  - Sensor
ha_release: 2022.12.1
ha_iot_class: Cloud Polling
ha_config_flow: true
ha_domain: combined_energy
ha_dhcp: false
ha_platforms:
  - binary_sensor
  - sensor
ha_codeowners:
  - '@timsavage'
ha_integration_type: device
---

The `combined_energy` integration lets you integrate your [Combined Energy](http://combined.energy/) Gateway
into your Home Assistant installation. The integration uses the API utilised by the [AtHome](https://athome.combined.energy/)
dashboard to provide access to devices exposed by the platform.

The Combined Energy Hub is commonly bundled with packages sold by other brands including Solahart.

There is currently support for the following device types within Home Assistant:

- [Binary Sensor](#binary-sensor)
- [Sensor](#sensor)

{% include integrations/config_flow.md %}

### Binary Sensor

The following binary sensors are added for each Powerwall:

- Energy Hub connection status - On/ Off

### Sensor

Each device type exposes multiple sensors with relevant information.


#### Solar PV

Sensors for a solar PV inverter.

- Energy Supplied - Amount of energy supplied by your inverter in kWh
- Power Supply - Amount power being supplied by your inverter at time of reading in kW

#### Water Heater

Sensors for a water heater.

- Energy Consumption - Total amount of energy being consumed in kWh
- Solar Energy Consumption - Amount of energy being consumed from solar sources in kWh  
- Battery Energy Consumption - Amount of energy being consumed from battery sources in kWh  
- Grid Energy Consumption - Amount of energy being consumed from the grid (imported) in kWh
- Power Consumption - Total power being consumed at time of reading in kW
- Solar Power Consumption - Amount of power being consumed from solar sources at time of reading in kW
- Battery Power Consumption - Amount of power being consumed from battery sources at time of reading in kW
- Grid Power Consumption - Amount of power being consumed from the grid (imported) at time of reading in kW

If connected to a smart water heater like a Solahart PowerStore

- Hot Water Available - Amount of hot water available for use in litres
- Hot Water Max - Maximum amount of hot water that can be provided in litres
- Output Temperature - Temperature of hot water at the outlet of the tank in °C
- Temp Sensor 1...6 - Temperature at up to six sensors (depending on the size of tank) at various levels within the tank in °C  

#### Grid Meter

Sensors for the Grid connection.

- Energy Import - Amount of energy imported from the grid in kWh
- Energy Export - Total amount of energy exported to the grid in kWh
- Energy Export Solar - Amount of energy exported to the grid from solar sources in kWh
- Energy Export Battery - Amount of energy exported to the grid from battery sources in kWh
- Power Import - Amount of power importing from the grid at time of reading in kW
- Power Export - Total amount of power exporting to the grid at time of reading in kW
- Power Export Solar - Amount of power exporting to the grid from solar sources at time of reading in kW
- Power Export Battery - Amount of power exporting to the grid from battery sources at time of reading in kW

Power factor and voltage sensors provide values for up to 3 phases if available.

- Power Factor A...C - Power factor of each phase in %
- Voltage - Current grid voltage of each phase in V

#### Energy Balance and Generic Consumer

Both of these device types provide the same sensors. Energy Balance is typically called Home in the default
dashboard where generic consumer is used for other devices e.g. Air Conditioners, Cooking Appliances etc.

- Energy Consumption - Total amount of energy being consumed in kWh
- Solar Energy Consumption - Amount of energy being consumed from solar sources in kWh  
- Battery Energy Consumption - Amount of energy being consumed from battery sources in kWh  
- Grid Energy Consumption - Amount of energy being consumed from the grid (imported) in kWh
- Power Consumption - Total power being consumed at time of reading in kW
- Solar Power Consumption - Amount of power being consumed from solar sources at time of reading in kW
- Battery Power Consumption - Amount of power being consumed from battery sources at time of reading in kW
- Grid Power Consumption - Amount of power being consumed from the grid (imported) at time of reading in kW

#### Battery

Battery sensors are not currently available. 