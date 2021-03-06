# MicroPython-VEML6075
 Driver base for the VEML6075 UV Light Sensor
 
> The VEML6075 senses UVA and UVB light and incorporates photodiode, amplifiers, and analog/digital circuits into a single chip using a CMOS process. When the UV sensor is applied, it is able to detect UVA and UVB intensity to provide a measure of the signal strength as well as allowing for UVI measurement.
 
### <b>DataSheet:</b>
https://www.digchip.com/datasheets/parts/datasheet/3951/VEML6075-pdf.php (in 09/21/2019) or file <i>['VEML6075_datasheet.pdf'](https://github.com/neliogodoi/MicroPython-VEML6075/blob/master/VEML6075_datasheet.pdf)</i><br>

## <b>Key features:</b>

* Package type: surface mount
* Dimensions (L x W x H in mm): 2.0 x 1.25 x 1.0
* Integrated modules: ultraviolet sensor (UV), and signal conditioning IC
* Converts solar UV light intensity to digital data
* Excellent UVA and UVB sensitivity
* Reliable performance of UV radiation measurement under long time solar UV exposure
* 16-bit resolution per channel
* UVA and UVB individual channel solution
* Low power consumption
* Temperature compensation: -40 °C to +85 °C
* Output type: I2C bus
* Operation voltage: 1.7V to 3.6V

## <b>Files:</b>

**'veml6075.py'**  Version for *Developers* of driver for geral devices compatibles of MicroPython - ESP8266, ESP32 and LoPy.<br>

**'veml6075_lowmem.py':** Version *Low Memory* of driver for geral devices compatibles of MicroPython - **No Documenteded**

## <b>Tests:</b>
#### ESP8266
```python
import veml6075
from machine import I2C, Pin

i2c = I2C(sda=Pin(4), scl=Pin(5))
sensor = veml6075.VEML6075(i2c=i2c)

sensor.uv_index
```
#### ESP32
```python
import  veml6075
from machine import I2C, Pin

i2c = I2C(sda=Pin(21), scl=Pin(22))
sensor = veml6075.VEML6075(i2c=i2c)

sensor.uv_index
```
#### LoPy
```python
import veml6075
from machine import I2C

i2c = I2C(0, I2C.MASTER, baudrate=100000)
sensor = veml6075.VEML6075(i2c=i2c)

sensor.uv_index
```

## <b>Driver Benchmark for Memory Consumed*:</b>
> MicroPython v1.11-8-g48dcbbe60 on 2019-05-29; ESP module with ESP8266

|       |ESP8266|ESP32|LoPy|
|------:|:-----:|:---:|:--:|
|Total Memory device (Kb)|64|520|200|
|MicroPython Consumes (kb)|31,75|388,25| |
|Memory Free (Kb)|32.25|111.75||
|Driver Uses  Memory  (Kb)|2.75|3.52|-|
