# Pre-patched Dexcom G7 App
## This patch is NOT the 'BYODA patch' and should not be confused with it, as this patch is a standalone and more minimalistic approach.

## Dexcom G7 v1.4.3906

Whats NEW in this version:
- Filsize increased to 177MB
- DEXCOM added heavy obfuscation
- Support and login for US users (US market launch)
- Improves battery life
- Glucose view in landscape mode
- Fixes some bug (which, we don't know - nice DEXCOM!)

## Patch v1.1 - modified funcionality:

- AndroidAPS glucose broadcasting (see here: https://androidaps.readthedocs.io/en/latest/Hardware/DexcomG7.html)
- Disable Dexcom compatibility check (will report a supported phone to DEXCOM)
- Decrease required android version
- Enable screenshots


# What is all of this?
This patch is NOT the "BYODA patch" and should not be confused with it, as this patch is a standalone, minimalist approach and has implemented more changes to the G7 app. 
This HOWTO / guide is intended to clear up many inconsistencies and half-knowledge and help the Dexcom G7 user to use the system even better.

## What is the Dexcom G7
In spring 2022, the Dexcom G7 received its CE certificate and was sold at the end of October ‘22 in EU states and starting February '23 in the US.
Noteworthy is the fact that the G7 system, compared to the predecessor G6, does not smooth or backsmooth (change past values to smooth out and smooth future values) the values, neither in the app, nor in the reader.  More details about this [here](https://www.dexcom.com/en-us/faqs/why-does-past-cgm-data-look-different-from-past-data-on-receiver-and-follow-app). Consequently, the values have to be smoothed (see below) to be able to use them sensibly in AndroidAPS. 

## Changes compared to the predecessor 
Compared to the predecessor, the G6, the warm-up time has been reduced to 30 minutes.
The sensor has a runtime of 10 days. At the end of the runtime of these 10 days, the sensor offers an additional 12h transition time. The warm-up time of a G7 sensor starts as soon as it leaves the setting aid and not when it is activated in the G7 app!

It is known that sensors can deliver erratic and incorrect values in the first 12-48 hours due to the injection trauma. Here it is advisable to use the 12h transition period so that the tissue can get used to the sensor. The following graphic explains the procedure:

[![g7-runtimes.png](https://i.postimg.cc/qv6nkWbW/g7-runtimes.png)](https://postimg.cc/DSFm6pKc)
1) Sensor A is set
2) After 10 days the grace period of 12 hours starts and exactly from this time sensor B is set but not activated in the app.
3) After these 12 hours, sensor A no longer provides any values and sensor B is activated in the app.


This method has several advantages:
1) Tissue can get used to the sensor and it will then provide more reliable values.
2) No time without sensor values
3) Runtime of a sensor is still 10 days

## What is this modified app?
To extend and limit the functionality of the original Dexcom G7 app, this version of the G7 app was created.

