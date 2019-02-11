# DHT22
🌡 Easily read from a DHT22 temp sensor in C

## Usage
Import header + imp files into your project. The reading bundles temperature and humidity, you can call either ```read_temperature_celsius``` or ```read_temperature_fahrenheit```, passing a GPIO pin, to read in either scale.

```C
#include "dht22.h"

struct DHT22 *reading = read_temperature_celsius(1);

printf("Temperature: %.2f *C\tHumidity: %.2f%%", 
	reading->temperature, reading->humidity);
```

e.g.
```
Temperature: 22.30 *C	Humidity: 37.00%
```

## Some notes
- Library assumes wiringPi is already initialized (this way you choose the pin configuration).
- Your pin requires no calibration, it is done with each reading.
- Due to the sensor itself, repeated polls should be made in at least 1000ms intervals.
- Original code was from an excerpt [here](https://github.com/ccoong7/DHT22) (I haven't removed the comments).
- A 10k pull up resistor should be placed between the positive and data lines.
