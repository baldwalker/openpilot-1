**OpenPilot 0.8.6**

<a href="https://www.paypal.com/donate?business=NRFAJ6FYRLT2Y&no_recurring=0&item_name=Contribute+to+help+progress+JPR%27s+HKG+Fork&currency_code=USD" 
target="_blank">
<img src="https://www.paypalobjects.com/en_US/GB/i/btn/btn_donateCC_LG.gif" alt="PayPal this" 
title="PayPal – The safer, easier way to pay online!" border="0" />
</a>
     Help Progress this fork along!
 
**Join our Discord here. https://discord.gg/zWSnqJ6rKD**

**This fork is community supported we appreciate all help! Too get involved join us on discord. https://discord.gg/zWSnqJ6rKD**

**Submit issues on the issues page in a detailed report on GitHub or for quick help post here in issues channel.  https://discord.gg/zWSnqJ6rKD**

This fork has full long control for all HKG and Harnessless for older 2015 & 2016 & 2017 Genesis G80(Fixed SMDPS) without any radar harness mod. All other cars should require scc to be moved to bus 2 from bus 0 for full long control. Test out HKG Long even if you don't have a harness. It might work and let me know if it works and your car isn't on this list.

**Reach out to johnpr#5623 on discord too buy a radar harness. MDPS harnesses are available for sale with a 1 1/2 week lead time. Software to control it is currently WIP**

**By using this software you are responsible for anything that occurs while OpenPilot is engaged or disengaged. Be ready to take over at any moment. Fork maintainers assumes no liability for your use of this software and any hardware.**

***Install***

***0.8.6***

Put this url during setup for stable https://smiskol.com/fork/Circuit-Pro/hkg_086

Put this url during setup for Dev https://smiskol.com/fork/Circuit-Pro/086_dev (Active development branch LOTS of changes made all the time. UNSTABLE)

***0.8.5***

Put this url during setup for stable https://smiskol.com/fork/Circuit-Pro/hkg_085

***2021 - 2020 Sonata***
 
In `Settings` under `Device` click the button that says "Fix" next to "Panda DAW warning fix for 2021 - 2020 Sonata".
 
***or***

run this command via ssh to temporarily fix D.A.W. (Driver Attention Warning) Resets on update for now. `cd /data/openpilot rm -r panda
git clone https://github.com/xps-genesis/panda.git -b xps_panda_daw
cd /data/openpilot/panda/board && make && reboot`

***If you installed from SSH***

- make sure too run `rm /data/params/d/DongleId` to reset your dongle ID.

***RetroPilot***

This fork uses RetroPilot for logging and online services.  https://api.retropilot.org/useradmin

Comma 2 has **POOR** performance with logging and uploader enabled so it's disabled by default. You can change that in `Settings` under `Community`.
     Contact johnpr#5623 for help with an Ubuntu installation and setup.

***nTune***
- nTune Auto Tunes lateral steering.

Run **nTune** after 30 - 50 miles of driving. It will autotune lateral control. Use this command `cd selfdrive && python ntune.py` or use the button in `Settings` under `Device`. (make sure your not driving!)

Make sure to **shut off** auto start stop or you will get steering temporarily unavailable if the engine shuts off.

Screen recording from ui **saved** to. `/storage/emulated/0/videos`

**Delete UI Screen Recordings button in `Settings` under `Device`.**

**Toggles**

- Toggles are in `Settings` under `Community`.

***Cluster Speed***

   - Uses the speed of the gauge cluster instead GPS speed.

***HKG Long control toggle. (radar + vision)***

   - Bring back my Lead Markers toggle for non HKG Longitudinal cars in `Community`. Not Recommended VERY MISSLEADING FOR STOCK LONGITUDINAL CARS
    - when Toggled on, replaces the default Hyundai / Kia / Genesis factory longitudinal control system (SCC) with the openpilot system. May be useful for systems that don’t currently HAVE SCC but can support SCC via openpilot when programmed to another car variant(same model) that has radar..

***Slow down for curves toggle. (Beta)***

   - allows openpilot to slow car when entering curves on HKG Long. 

***LDWS toggle***
   - under `Community` in `Settings` for cars with LDWS but not SCC.

***Show Debug UI***

   - I feel like you should understand what “debugging” and a “UI” are before you can use openpilot

***Use SMDPS Harness***

   - Use of MDPS Harness to enable openpilot steering down to 0 MPH


***Stop Screen Capture on disengage toggle.***

***WiFi Hot Spot Auto Start on drive toggle.***

***End WiFi Hot Spot on end of drive toggle.***

***On screen blinkers and blind spot alerts.***

***Enable Lane Change Assist***

  - allows openpilot to change lanes. Driver is responsible for ensuring that it is SAFE to change lanes. Requires signal, and steering wheel nudge.

***Auto Lane Change with Blind spot monitoring toggle (No Nudge).***
  - Same as the original, now with 100% less nudge.

***Sync Speed on Gas Press***

  - openpilot will sync cruise control set speed to match last attained speed automatically

***Smooth SCC with SCC smoother.***

***Use by fusion with stock SCC***
   If applicable stock SCC will control gas and OP will control braking, it will smooth out the late abrupt braking from stock SCC.

***Make sure to reboot with toggle changes.***

Then give it a spin.

***Behavior Notes***

OpenPilot will not see totally stopped cars yet until E2E comes so do not trust it to see and stop for a COMPLETLY stopped car.

If Collision Warning is beeping at you OpenPilot has calculated it can't stop quick enough due to safety limitations on unintentional braking. Please apply brakes to avoid collision.



**This is based on xx979xx & Neokii's & crwusiz's fork and is tuned for Genesis G70, Kia Stinger, and works on others but not tested..**

https://github.com/neokii/op4

https://github.com/xx979xx/openpilot

https://github.com/crwusiz/openpilot

**Unlimited data, data only simcard compatible with C2.**

https://www.amazon.com/dp/B07JCTZ3BF/ref=cm_sw_r_u_apa_glt_fabc_SNA9EVB27NT0DPRMEY3Q?psc=1

Run `adb shell am start -a android.settings.SETTINGS` and go too `"SIM cards"` and under `Cellular network settings` choose either "SIM 1 settings" or "SIM 2 settings" (based on which slot you have your non comma sim installed in.) Then go to `Access Point Names` add and set APN name correctly for sim provider(for the one i'm using and linked above the APN username is `m2mglobal` leave everything else default or blank. (MCC 310, MNC 260)

**MDPS/SMDPS** Refrence these guides to build one. 
- https://github.com/Circuit-Pro/openpilot/blob/main/Hyundai_MDPS_Comma_Harness.pdf 
- https://github.com/Circuit-Pro/openpilot/blob/main/Pinout%20For%20CommaPower%20to%20Micro64.pdf 
- https://medium.com/@kyroapps/adding-support-for-lateral-control-below-51km-h-for-hyundai-vehicles-10be0b556371

Kia Niro MDPS ECU - http://www.kniro.net/schematic_diagrams-1321.html

MDPS Connectors

Male
- https://www.mouser.com/ProductDetail/aptiv/15420151/?qs=WTe5OP3w0Koiy%252bx6KqjpIQ%3D%3D&countrycode=CA&currencycode=CAD&bm-verify=AAQAAAAD_____xGvBoTAT_yusRfcDbPOvmmaN_N4VgvTUsLpnvbpGb1zClm2LRJZFYrTQaCWy30sxMrw5LMiUOXCn06a49I1B8zA96meyl7U7I8EteiPj05-qHB8w3slUdlaiAvam3Y96_Xsl81g3qPzp08LwevFanhLa8jvAmcmYyFsMkQVmB5o-bjjk2E3sWqFDi3jINO2kCMPiDZ2BYdawKzl7yPNrkc_dq8iwl-oyNoa242w_dFKI5z1ucS22Etf-_dT-L09e7XFLzVQ307lPqcZrR0mu1gqEY94MN4p9yj71EYVH8SrUJAFu9UOAa0l9ATl01niGRC6afmOr91rzh087B1Bj6RXGml62nkMWgBDkGsiWU7DRkPUjfVJZu00hioYwl-A758CMrxFB3GHEQm-V7oT8kdHI7i-9TH5oxRgrArVhcDlAGasgzhKrWwJ0CXP9okjrQbhlcFZeVPvfQW4RP3WJkHUJnUna-wRSzX2J4Fr7jJBRKDsu7oGqJNSIbsioIlbHsb5-B5Zoi_bLnA0

Female 
- https://www.mouser.com/ProductDetail/aptiv/15406142/?qs=xyz6lfZ1ktKtmezTNc3DLw%3D%3D&countrycode=CA&currencycode=CAD
- https://www.mouser.com/ProductDetail/aptiv/15401440-l/?qs=NKHyz0HolODmWpNAvMSDSg%3D%3D&countrycode=CA&currencycode=CAD

Black Panda
- https://github.com/Circuit-Pro/openpilot/blob/main/648E3090-698D-4568-BCEE-E723442B3C00.jpeg

RJ45 female connectors
- https://www.amazon.com/dp/B07JRD69V6/ref=cm_sw_r_cp_api_glt_fabc_WTRZRMNRG20KSPHKRQSX?_encoding=UTF8&psc=1

RJ45 black panda and comma power adapter
- https://github.com/Circuit-Pro/openpilot/blob/main/C50DC3FD-B803-4B67-A435-AA857EF2396B.png


It is open source and inherits MIT license. It is open source and inherits MIT license.  By installing this software you accept all responsibility for anything that might occur while you use it.  All contributors to this fork are not liable.  <b>Use at your own risk.</b>
------------------------------------------------------


[![](https://i.imgur.com/UelUjKAh.png)](#)

Table of Contents
=======================

* [What is openpilot?](#what-is-openpilot)
* [Integration with Stock Features](#integration-with-stock-features)
* [Supported Hardware](#supported-hardware)
* [Supported Cars](#supported-cars)
* [Community Maintained Cars and Features](#community-maintained-cars-and-features)
* [Installation Instructions](#installation-instructions)
* [Limitations of openpilot ALC and LDW](#limitations-of-openpilot-alc-and-ldw)
* [Limitations of openpilot ACC and FCW](#limitations-of-openpilot-acc-and-fcw)
* [Limitations of openpilot DM](#limitations-of-openpilot-dm)
* [User Data and comma Account](#user-data-and-comma-account)
* [Safety and Testing](#safety-and-testing)
* [Testing on PC](#testing-on-pc)
* [Community and Contributing](#community-and-contributing)
* [Directory Structure](#directory-structure)
* [Licensing](#licensing)

---

What is openpilot?
------

[openpilot](http://github.com/commaai/openpilot) is an open source driver assistance system. Currently, openpilot performs the functions of Adaptive Cruise Control (ACC), Automated Lane Centering (ALC), Forward Collision Warning (FCW) and Lane Departure Warning (LDW) for a growing variety of supported [car makes, models and model years](#supported-cars). In addition, while openpilot is engaged, a camera based Driver Monitoring (DM) feature alerts distracted and asleep drivers.

<table>
  <tr>
    <td><a href="https://www.youtube.com/watch?v=mgAbfr42oI8" title="YouTube" rel="noopener"><img src="https://i.imgur.com/kAtT6Ei.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=394rJKeh76k" title="YouTube" rel="noopener"><img src="https://i.imgur.com/lTt8cS2.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=1iNOc3cq8cs" title="YouTube" rel="noopener"><img src="https://i.imgur.com/ANnuSpe.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=Vr6NgrB-zHw" title="YouTube" rel="noopener"><img src="https://i.imgur.com/Qypanuq.png"></a></td>
  </tr>
  <tr>
    <td><a href="https://www.youtube.com/watch?v=Ug41KIKF0oo" title="YouTube" rel="noopener"><img src="https://i.imgur.com/3caZ7xM.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=NVR_CdG1FRg" title="YouTube" rel="noopener"><img src="https://i.imgur.com/bAZOwql.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=tkEvIdzdfUE" title="YouTube" rel="noopener"><img src="https://i.imgur.com/EFINEzG.png"></a></td>
    <td><a href="https://www.youtube.com/watch?v=_P-N1ewNne4" title="YouTube" rel="noopener"><img src="https://i.imgur.com/gAyAq22.png"></a></td>
  </tr>
</table>

Integration with Stock Features
------

In all supported cars:
* Stock Lane Keep Assist (LKA) and stock ALC are replaced by openpilot ALC, which only functions when openpilot is engaged by the user.
* Stock LDW is replaced by openpilot LDW.

Additionally, on specific supported cars (see ACC column in [supported cars](#supported-cars)):
* Stock ACC is replaced by openpilot ACC.
* openpilot FCW operates in addition to stock FCW.

openpilot should preserve all other vehicle's stock features, including, but are not limited to: FCW, Automatic Emergency Braking (AEB), auto high-beam, blind spot warning, and side collision warning.

Supported Hardware
------

At the moment, openpilot supports the [comma two](https://comma.ai/shop/products/comma-two-devkit). A [car harness](https://comma.ai/shop/products/car-harness) is recommended to connect the EON or comma two to the car. For experimental purposes, openpilot can also run on an Ubuntu computer with external [webcams](https://github.com/commaai/openpilot/tree/master/tools/webcam).

Community Maintained Cars and Features
------

| Make      | Model (US Market Reference)   | Supported Package | ACC              | No ACC accel below | No ALC below |
| ----------| ------------------------------| ------------------| -----------------| -------------------| -------------|
| Genesis   | G70 2018                      | All               | OpenPilot            | 0mph               | 0mph         |
| Genesis   | G80 2017                      | All               | OpenPilot            | 0mph               | 35mph        |
| Genesis   | G80 2018                      | All               | OpenPilot            | 0mph               | 0mph         |
| Genesis   | G90 2018                      | All               | OpenPilot            | 0mph               | 0mph         |
| Hyundai   | Elantra 2017-19, 2021         | SCC + LKAS        | Stock            | 19mph              | 0mph w MDPS Harness        |
| Hyundai   | Genesis 2015-16               | SCC + LKAS        | OpenPilot            | 19mph              | 37mph        |
| Hyundai   | Ioniq Electric 2019           | SCC + LKAS        | Stock            | 0mph               | 32mph        |
| Hyundai   | Ioniq Electric 2020           | SCC + LKAS        | Stock            | 0mph               | 0mph         |
| Hyundai   | Kona 2020                     | SCC + LKAS        | Stock            | 0mph               | 0mph         |
| Hyundai   | Kona EV 2019                  | SCC + LKAS        | OP w Radar Harness    | 0mph               | 0mph w MDPS Harness         |
| Hyundai   | Santa Fe 2019-20              | All               | Stock            | 0mph               | 0mph         |
| Hyundai   | Sonata 2018-2019              | SCC + LKAS        | Stock            | 0mph               | 0mph         |
| Hyundai   | Veloster 2019                 | SCC + LKAS        | Stock            | 5mph               | 0mph         |
| Kia       | Forte 2018-2021               | SCC + LKAS        | Stock            | 0mph               | 0mph         |
| Kia       | Niro EV 2020                  | SCC + LKAS        | OP w Radar Harness    | 0mph          | 0mph         |
| Kia	  | Niro PHEV 2019                |	SCC + LKAS    | Stock            |	        10mph      | 0mph w MDPS Harness        |
| Kia       | Optima 2017                   | SCC + LKAS        | Stock            | 0mph               | 0mph w MDPS Harness        |
| Kia       | Optima 2019                   | SCC + LKAS        | Stock            | 0mph               | 0mph         |
| Kia       | Seltos 2021                   | SCC + LKAS        | Stock            | 0mph               | 0mph         |
| Kia       | Sorento 2018-19               | SCC + LKAS        | Stock            | 0mph               | 0mph         |
| Kia       | Stinger 2018                  | SCC + LKAS        | OP w Radar Harness     | 0mph               | 0mph         |
| Kia       | Ceed 2019                     | SCC + LKAS        | Stock            | 0mph               | 0mph         |


Community Maintained Cars and Features are not verified by comma to meet our [safety model](SAFETY.md). Be extra cautious using them. They are only available after enabling the toggle in `Settings->Developer->Enable Community Features`.

Community Maintained Cars and Features are not verified by comma to meet our [safety model](SAFETY.md). Be extra cautious using them. They are only available after enabling the toggle in `Settings->Developer->Enable Community Features`.

To promote a car from community maintained, it must meet a few requirements. We must own one from the brand, we must sell the harness for it, has full ISO26262 in both panda and openpilot, there must be a path forward for longitudinal control, it must have AEB still enabled, and it must support fingerprinting 2.0

Although they're not upstream, the community has openpilot running on other makes and models. See the 'Community Supported Models' section of each make [on our wiki](https://wiki.comma.ai/).

Installation Instructions
------

Install openpilot on an EON or comma two by entering ``https://openpilot.comma.ai`` during the installer setup.

Follow these [video instructions](https://youtu.be/lcjqxCymins) to properly mount the device on the windshield. Note: openpilot features an automatic pose calibration routine and openpilot performance should not be affected by small pitch and yaw misalignments caused by imprecise device mounting.

Before placing the device on your windshield, check the state and local laws and ordinances where you drive. Some state laws prohibit or restrict the placement of objects on the windshield of a motor vehicle.

You will be able to engage openpilot after reviewing the onboarding screens and finishing the calibration procedure.

Limitations of openpilot ALC and LDW
------

openpilot ALC and openpilot LDW do not automatically drive the vehicle or reduce the amount of attention that must be paid to operate your vehicle. The driver must always keep control of the steering wheel and be ready to correct the openpilot ALC action at all times.

While changing lanes, openpilot is not capable of looking next to you or checking your blind spot. Only nudge the wheel to initiate a lane change after you have confirmed it's safe to do so.

Many factors can impact the performance of openpilot ALC and openpilot LDW, causing them to be unable to function as intended. These include, but are not limited to:

* Poor visibility (heavy rain, snow, fog, etc.) or weather conditions that may interfere with sensor operation.
* The road facing camera is obstructed, covered or damaged by mud, ice, snow, etc.
* Obstruction caused by applying excessive paint or adhesive products (such as wraps, stickers, rubber coating, etc.) onto the vehicle.
* The device is mounted incorrectly.
* When in sharp curves, like on-off ramps, intersections etc...; openpilot is designed to be limited in the amount of steering torque it can produce.
* In the presence of restricted lanes or construction zones.
* When driving on highly banked roads or in presence of strong cross-wind.
* Extremely hot or cold temperatures.
* Bright light (due to oncoming headlights, direct sunlight, etc.).
* Driving on hills, narrow, or winding roads.

The list above does not represent an exhaustive list of situations that may interfere with proper operation of openpilot components. It is the driver's responsibility to be in control of the vehicle at all times.

Limitations of openpilot ACC and FCW
------

openpilot ACC and openpilot FCW are not systems that allow careless or inattentive driving. It is still necessary for the driver to pay close attention to the vehicle’s surroundings and to be ready to re-take control of the gas and the brake at all times.

Many factors can impact the performance of openpilot ACC and openpilot FCW, causing them to be unable to function as intended. These include, but are not limited to:

* Poor visibility (heavy rain, snow, fog, etc.) or weather conditions that may interfere with sensor operation.
* The road facing camera or radar are obstructed, covered, or damaged by mud, ice, snow, etc.
* Obstruction caused by applying excessive paint or adhesive products (such as wraps, stickers, rubber coating, etc.) onto the vehicle.
* The device is mounted incorrectly.
* Approaching a toll booth, a bridge or a large metal plate.
* When driving on roads with pedestrians, cyclists, etc...
* In presence of traffic signs or stop lights, which are not detected by openpilot at this time.
* When the posted speed limit is below the user selected set speed. openpilot does not detect speed limits at this time.
* In presence of vehicles in the same lane that are not moving.
* When abrupt braking maneuvers are required. openpilot is designed to be limited in the amount of deceleration and acceleration that it can produce.
* When surrounding vehicles perform close cut-ins from neighbor lanes.
* Driving on hills, narrow, or winding roads.
* Extremely hot or cold temperatures.
* Bright light (due to oncoming headlights, direct sunlight, etc.).
* Interference from other equipment that generates radar waves.

The list above does not represent an exhaustive list of situations that may interfere with proper operation of openpilot components. It is the driver's responsibility to be in control of the vehicle at all times.

Limitations of openpilot DM
------

openpilot DM should not be considered an exact measurement of the alertness of the driver.

Many factors can impact the performance of openpilot DM, causing it to be unable to function as intended. These include, but are not limited to:

* Low light conditions, such as driving at night or in dark tunnels.
* Bright light (due to oncoming headlights, direct sunlight, etc.).
* The driver's face is partially or completely outside field of view of the driver facing camera.
* The driver facing camera is obstructed, covered, or damaged.

The list above does not represent an exhaustive list of situations that may interfere with proper operation of openpilot components. A driver should not rely on openpilot DM to assess their level of attention.

User Data and comma Account
------

By default, openpilot uploads the driving data to our servers. You can also access your data by pairing with the comma connect app ([iOS](https://apps.apple.com/us/app/comma-connect/id1456551889), [Android](https://play.google.com/store/apps/details?id=ai.comma.connect&hl=en_US)). We use your data to train better models and improve openpilot for everyone.

openpilot is open source software: the user is free to disable data collection if they wish to do so.

openpilot logs the road facing camera, CAN, GPS, IMU, magnetometer, thermal sensors, crashes, and operating system logs.
The driver facing camera is only logged if you explicitly opt-in in settings. The microphone is not recorded.

By using openpilot, you agree to [our Privacy Policy](https://my.comma.ai/privacy). You understand that use of this software or its related services will generate certain types of user data, which may be logged and stored at the sole discretion of comma. By accepting this agreement, you grant an irrevocable, perpetual, worldwide right to comma for the use of this data.

Safety and Testing
----

* openpilot observes ISO26262 guidelines, see [SAFETY.md](SAFETY.md) for more details.
* openpilot has software in the loop [tests](.github/workflows/test.yaml) that run on every commit.
* The safety model code lives in panda and is written in C, see [code rigor](https://github.com/commaai/panda#code-rigor) for more details.
* panda has software in the loop [safety tests](https://github.com/commaai/panda/tree/master/tests/safety).
* Internally, we have a hardware in the loop Jenkins test suite that builds and unit tests the various processes.
* panda has additional hardware in the loop [tests](https://github.com/commaai/panda/blob/master/Jenkinsfile).
* We run the latest openpilot in a testing closet containing 10 EONs continuously replaying routes.

Testing on PC
------
For simplified development and experimentation, openpilot can be run in the CARLA driving simulator, which allows you to develop openpilot without a car. The whole setup should only take a few minutes.

Steps:
1) Start the CARLA server on first terminal
```
bash -c "$(curl https://raw.githubusercontent.com/commaai/openpilot/master/tools/sim/start_carla.sh)"
```
2) Start openpilot on second terminal
```
bash -c "$(curl https://raw.githubusercontent.com/commaai/openpilot/master/tools/sim/start_openpilot_docker.sh)"
```
3) Press 1 to engage openpilot

See the full [README](tools/sim/README.md)

You should also take a look at the tools directory in master: lots of tools you can use to replay driving data, test, and develop openpilot from your PC.


Community and Contributing
------

openpilot is developed by [comma](https://comma.ai/) and by users like you. We welcome both pull requests and issues on [GitHub](http://github.com/commaai/openpilot). Bug fixes and new car ports are encouraged.

You can add support for your car by following guides we have written for [Brand](https://medium.com/@comma_ai/how-to-write-a-car-port-for-openpilot-7ce0785eda84) and [Model](https://medium.com/@comma_ai/openpilot-port-guide-for-toyota-models-e5467f4b5fe6) ports. Generally, a car with adaptive cruise control and lane keep assist is a good candidate. [Join our Discord](https://discord.comma.ai) to discuss car ports: most car makes have a dedicated channel.

Want to get paid to work on openpilot? [comma is hiring](https://comma.ai/jobs/).

And [follow us on Twitter](https://twitter.com/comma_ai).

Directory Structure
------
    .
    ├── cereal              # The messaging spec and libs used for all logs
    ├── common              # Library like functionality we've developed here
    ├── installer/updater   # Manages auto-updates of NEOS
    ├── opendbc             # Files showing how to interpret data from cars
    ├── panda               # Code used to communicate on CAN
    ├── phonelibs           # Libraries used on NEOS devices
    ├── pyextra             # Libraries used on NEOS devices
    └── selfdrive           # Code needed to drive the car
        ├── assets          # Fonts, images and sounds for UI
        ├── athena          # Allows communication with the app
        ├── boardd          # Daemon to talk to the board
        ├── camerad         # Driver to capture images from the camera sensors
        ├── car             # Car specific code to read states and control actuators
        ├── common          # Shared C/C++ code for the daemons
        ├── controls        # Perception, planning and controls
        ├── debug           # Tools to help you debug and do car ports
        ├── locationd       # Soon to be home of precise location
        ├── logcatd         # Android logcat as a service
        ├── loggerd         # Logger and uploader of car data
        ├── modeld          # Driving and monitoring model runners
        ├── proclogd        # Logs information from proc
        ├── sensord         # IMU / GPS interface code
        ├── test            # Unit tests, system tests and a car simulator
        └── ui              # The UI

Licensing
------

openpilot is released under the MIT license. Some parts of the software are released under other licenses as specified.

Any user of this software shall indemnify and hold harmless comma.ai, Inc. and its directors, officers, employees, agents, stockholders, affiliates, subcontractors and customers from and against all allegations, claims, actions, suits, demands, damages, liabilities, obligations, losses, settlements, judgments, costs and expenses (including without limitation attorneys’ fees and costs) which arise out of, relate to or result from any use of this software by user.

**THIS IS ALPHA QUALITY SOFTWARE FOR RESEARCH PURPOSES ONLY. THIS IS NOT A PRODUCT.
YOU ARE RESPONSIBLE FOR COMPLYING WITH LOCAL LAWS AND REGULATIONS.
NO WARRANTY EXPRESSED OR IMPLIED.**

---

<img src="https://d1qb2nb5cznatu.cloudfront.net/startups/i/1061157-bc7e9bf3b246ece7322e6ffe653f6af8-medium_jpg.jpg?buster=1458363130" width="75"></img> <img src="https://cdn-images-1.medium.com/max/1600/1*C87EjxGeMPrkTuVRVWVg4w.png" width="225"></img>

[![openpilot tests](https://github.com/commaai/openpilot/workflows/openpilot%20tests/badge.svg?event=push)](https://github.com/commaai/openpilot/actions)
[![Total alerts](https://img.shields.io/lgtm/alerts/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/alerts/)
[![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:python)
[![Language grade: C/C++](https://img.shields.io/lgtm/grade/cpp/g/commaai/openpilot.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/commaai/openpilot/context:cpp)
[![codecov](https://codecov.io/gh/commaai/openpilot/branch/master/graph/badge.svg)](https://codecov.io/gh/commaai/openpilot)

