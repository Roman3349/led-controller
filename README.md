# ![led-controller](https://raw.githubusercontent.com/Roman3349/led-controller/master/artwork/logo.png)

[![Travis CI](https://img.shields.io/travis/Roman3349/led-controller.svg?style=flat-square)](https://travis-ci.org/Roman3349/led-controller)
[![Gitter](https://img.shields.io/gitter/room/Roman3349/led-controller.svg?style=flat-square)](https://gitter.im/Roman3349/led-controller)
[![GPLv3](http://img.shields.io/badge/license-GPLv3-blue.svg?style=flat-square)](LICENSE)

Arduino project to control RGB LED strip

## Part list
 - IQRF Development set [IQRF DS-START-04](http://eshop.iqrf.org/products/detail/DS-START-04)
 - IQRF Breakout board [IQRF BB-01](http://eshop.iqrf.org/products/detail/IQRF-BB-01)
 - IQRF gateway (for example [IQRF GW-ETH-02A](http://eshop.iqrf.org/products/detail/GW-ETH-02A%2872D%29))
 - Atmel MCU with Arduino firmware or Adruino (for example [Arduino Nano](http://www.tme.eu/en/details/a000005/arduino-development-kits/arduino/arduino-nano/))
 - 3x [STMicroelectronics TIP122](http://www.tme.eu/en/details/tip122/npn-tht-darlington-transistors/st-microelectronics/)
 - 5V voltage stabiliser (for example [ON Semiconductor MC78M05CTG](http://www.tme.eu/en/details/mc78m05ctg/unregulated-voltage-regulators/on-semiconductor/))
 - RGB LED strip (for example [OptoFlash OPRGB5060-6012B](http://www.tme.eu/en/details/oprgb5060-6012b/light-sources-led-ribbon/optoflash/))
 - 5,5/2,1mm DC jack (for example [CLIFF FC68148](http://www.tme.eu/en/details/fc68148/dc-power-connectors/cliff/))
 - 12V power supply (for example [ESPE ZSIDT12/3A](http://www.tme.eu/en/details/zsidt12_3a/mains-power-supplies/espe/))
 - terminal block PCB mount (for example [Degson Electronics DG300-5.0-02P-12-00A(H)](http://www.tme.eu/en/details/dg300-5.0-2p12/terminal-blocks-pcb-mount/degson-electronics/dg300-50-02p-12-00ah/))

## Arduino libraries

 * [IQRF](https://github.com/iqrfsdk/clibiqrf-arduino)
 * [MsTimer2](https://github.com/PaulStoffregen/MsTimer2)

## Packets

### Ping
<table>
<tr>
<th>0-FF</th>
<th>100-1FF</th>
<th>200-2FF</th>
<th>300-3FF</th>
<th>400-4FF</th>
<th>500-5FF</th>
</tr>
<tr>
<td>version</td>
<td>type</td>
<td colspan="4">address</td>
</tr>
<tr>
<td>0</td>
<td>0</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
</tr>
</table>

### Pong
<table>
<tr>
<th>0-FF</th>
<th>100-1FF</th>
<th>200-2FF</th>
<th>300-3FF</th>
<th>400-4FF</th>
<th>500-5FF</th>
</tr>
<tr>
<td>version</td>
<td>type</td>
<td colspan="4">address</td>
</tr>
<tr>
<td>0</td>
<td>1</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
</tr>
</table>

### Set color
<table>
<tr>
<th>00-FF</th>
<th>100-1FF</th>
<th>200-2FF</th>
<th>300-3FF</th>
<th>400-4FF</th>
<th>500-5FF</th>
<th>600-6FF</th>
<th>700-7FF</th>
<th>800-8FF</th>
<th>900-9FF</th>
</tr>
<tr>
<td>version</td>
<td>type</td>
<td colspan="4">address</td>
<td>red</td>
<td>green</td>
<td>blue</td>
<td>alpha</td>
</tr>
<tr>
<td>0</td>
<td>2</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-FF</td>
<td>0-1</td>
</tr>
</table>

## Schema
### Prototype
![Schema](https://gitlab.com/Roman3349/led-controller/raw/master/eagle/prototype/schema.png)
### Production
![Schema](https://gitlab.com/Roman3349/led-controller/raw/master/eagle/production/schema.png)

## License
led-controller is licensed under the GPLv3 license:

 > Copyright (C) 2016 Roman Ondráček
 > 
 > This program is free software: you can redistribute it and/or modify
 > it under the terms of the GNU General Public License as published by
 > the Free Software Foundation, either version 3 of the License, or
 > (at your option) any later version.
 > 
 > This program is distributed in the hope that it will be useful,
 > but WITHOUT ANY WARRANTY; without even the implied warranty of
 > MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 > GNU General Public License for more details.
 > 
 > You should have received a copy of the GNU General Public License
 > along with this program.  If not, see <http://www.gnu.org/licenses/>.
