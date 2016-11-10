# KY-040-Encoder-Library---Arduino
Arduino library for the KY-040 Encoder. 

This library allows the user to connect up to two encoders using interrupts 0 (pin D3) and interrupt 1 (pin D2). The user may then add rotaries that will each keep track of the encoder movement while active. Each rotary is initialized with the rotary ID (a byte value between 0 - 254), an initial integer value, and integer values for minimum, maximum, and increment. Also a boolean rollover flag controls whether the current rotary value wraps from min to max or max to min.

Note, memory for the total number of rotaries for an encoder is allocated during object creation. If you attempt to add a rotary (using AddRotaryCounter) beyond the limit set during object creation, the function will fail.

The KY-040 encoder library uses interrupts on the clock line. Because of switch bounces, a 470 nF (0.47 uF) capacitor is required on each encoder clock pin connected from the Arduino pin to ground. https://cloud.githubusercontent.com/assets/3778024/20186507/ef862cfc-a735-11e6-9f66-3f124f1604f1.png.

Another 470 nF capacitor is required on the encoder switch pin, connected between the Arduino pin and ground.

The code has been tested on an Arduino Micro. See the Examples directory. Also, a sketch using multiple rotaries for one encoder may be found under https://github.com/Billwilliams1952/Arduino-Controlled-Fan-Tester
