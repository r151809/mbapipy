# mbapipy

MercedesME platform as a Custom Component for Home Assistant.

Remove other MercedesMe components before use of this one.

Configuration:
```
mercedesmeapi:
  username: YOUR_USERNAME
  password: YOUR_PASSWORD
```

Optional configuration values
```
mercedesmeapi:
  username: YOUR_USERNAME
  password: YOUR_PASSWORD
  pin: XXXX                      # need to open the lock, please use the Mercedes web or app to set-up the pin
  
  country_code: DE               # two digts country code
  accept_lang: en_DE             # four digits country code
  save_car_details: true         # save a json to the HA config directory with the features and states, please use this for debug only 
```

Available components:
- Lock
- Aux Heat Switch

- Binary Sensors:
```
- warningenginelight
  attributes: warningbrakefluid, warningwashwater, warningcoolantlevellow, warninglowbattery

- parkbrakestatus
  attributes: preWarningBrakeLiningWear

- windowsClosed
  attributes: windowstatusrearleft, windowstatusrearright, windowstatusfrontright, windowstatusfrontleft

- tirewarninglamp
  attributes: tirepressureRearLeft, tirepressureRearRight, tirepressureFrontRight, tirepressureFrontLeft, tirewarningsrdk, tirewarningsprwtireMarkerFrontRight, tireMarkerFrontLeft, tireMarkerRearLeft, tireMarkerRearRight, tireWarningRollup, lastTirepressureTimestamp
```

- Sensors:
```
- lock
  attributes: doorStateFrontLeft, doorStateFrontRight, doorStateRearLeft, doorStateRearRight, frontLeftDoorLocked, frontRightDoorLocked, rearLeftDoorLocked, rearRightDoorLocked, frontLeftDoorClosed, frontRightDoorClosed, rearLeftDoorClosed, rearRightDoorClosed, rearRightDoorClosed, doorsClosed, trunkStateRollup, sunroofstatus

- rangeElectricKm
  attributes: rangeelectric, rangeElectricKm, criticalStateOfSoc, maxrange, stateOfChargeElectricPercent, endofchargetime, criticalStateOfDeparturetimesoc, warninglowbattery, electricconsumptionreset, maxStateOfChargeElectricPercent, supplybatteryvoltage, electricChargingStatus, chargingstatus, soc, showChargingErrorAndDemand, electricconsumptionstart
  
- auxheatstatus
  attributes: auxheatActive, auxheatwarnings, auxheatruntime, auxheatwarningsPush, auxheattimeselection, auxheattime1, auxheattime2, auxheattime3

- tanklevelpercent

- odometer
  attributes: distanceReset, distanceStart, averageSpeedReset, averageSpeedStart, distanceZEReset, drivenTimeZEReset, drivenTimeReset, drivenTimeStart, ecoscoretotal, ecoscorefreewhl, ecoscorebonusrange, ecoscoreconst, ecoscoreaccel, gasconsumptionstart, gasconsumptionreset, gasTankRange, gasTankLevel, liquidconsumptionstart, liquidconsumptionreset, liquidRangeSkipIndication, rangeliquid, serviceintervaldays, tanklevelpercent, tankReserveLamp
  
```


Logging:
Set the logging to debug with the following settings in case of problems.
```
logger:
  default: warn
  logs:
    custom_components.mercedesmeapi: debug
    custom_components.mercedesmeapi.sensor: info
    custom_components.mercedesmeapi.apicontroller: debug
    custom_components.mercedesmeapi.OAuth: debug
```

