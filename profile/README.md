# OpenHumidistat

Here you can find the sources for the firmware, software utilities, and hardware of OpenHumidistat, a free and open-source humidistat for laboratory-scale humidity control that is affordable and easy to build.

Using OpenHumidistat, you can realise humidity control for your experimental setups for about €500 (and some of your time to build it). OpenHumidistat is designed to provide standalone control of the humidity in a small measurement chamber (~ 10 - 100 mL). It features:

- Fast and precise dynamic response
  - Settling time of ~ 10 s
- Broad attainable humidity range of approximately 10-90% (depending on humidifier efficacy and feed gas conditions)
- Flowrate up to 2 L/min
- High accuracy and good disturbance rejection through closed-loop control
- Easy and intuitive operation
- Excellent versatility and portability: can be applied to a wide range of experimental setups
- Optional monitoring/logging of controller state using Python utility on a PC connected over USB

The design is based around mixing a humid and dry air flow in varying proportions, using proportional solenoid valves and flow sensors to control flow rates. The mixed flow is led into a measurement chamber, which contains a humidity sensor to provide feedback to the controller, to achieve closed-loop humidity control.

![](https://github.com/OpenHumidistat/.github/assets/7603719/243d1c5d-ea67-41aa-9bef-213ebf1f45db)

There are two versions of the humidistat, the development of which are described in the two papers listed below.

v1             |  v2 (OpenHumidistat)
:-------------------------:|:-------------------------:
<img src="https://github.com/OpenHumidistat/.github/assets/7603719/bfd68dd0-57cc-4cd7-b9a4-9fbe3d1202de" width="500px">  | <img src="https://github.com/OpenHumidistat/.github/assets/7603719/b80bd339-9c06-4d26-a08a-2af10616c3df" width="500px">

The second version features upgraded components including a much more powerful microcontroller and better humidity sensor, performance and stability improvements to the controller itself (cascade PID control using flow sensors), a much fancier interface, and on-the-fly configurability.

## Getting started

If you are interested in building OpenHumidistat, it is strongly recommended to consider the second version. Besides upgrades to the hardware, [the article describing it](https://arxiv.org/pdf/2112.08500) includes comprehensive step-by-step build instructions. PCB designs for the custom circuits and 3D models for the enclosure are also provided for your convenience.

## Addenda

### Cooling
It was found that the heat from the solenoid valves could affect the temperature in the measurement chamber. To alleviate this issue, a (60 mm) fan can be installed in the OpenHumidistat enclosure. Updated CAD files, as well as an updated version of the solenoid driver PCB with a fan header, are available to this end.

### Teensy 4.0 compatiblity
The Teensy LC microcontroller board is getting less and less available due to supply issues with its microcontroller chip. Instead, the [Teensy 4.0](https://www.pjrc.com/store/teensy40.html) can be used as a drop-in replacement. It is pin-compatible and an upgrade in terms of specifications compared to the Teensy LC. The firmware has been prepared for compatibility with the Teensy 4.0.

## Publications
First version, using Arduino Uno, single-loop PID controller, DHT22/AM2302 humidity sensor, and 16x2 character display:

Veldscholte, L.B., Horst, R.J. & de Beer, S.  
Design, construction, and testing of an accurate low-cost humidistat for laboratory-scale applications.  
Eur. Phys. J. E 44, 48 (2021).  
https://doi.org/10.1140/epje/s10189-021-00062-5

Second, improved version, using Teensy LC, cascade PID controller, SHT85 humidity sensor, and 128x64 graphical display:

Veldscholte, L. B., de Beer, S.  
OpenHumidistat: Humidity-controlled experiments for everyone.  
HardwareX 11, e00288 (2022).  
https://doi.org/10.1016/j.ohx.2022.e00288

If you are using OpenHumidistat in your research, it is much appreciated if you cite the relevant paper(s).
