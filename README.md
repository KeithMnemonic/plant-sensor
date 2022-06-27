- [Introduction](#introduction)



# Introduction
This project contains the artifacts I am using to implement a plant moisture sensor that will integrate with [Home Assistant](https://www.home-assistant.io/). All of the sensors are using a [Capacitive Soil Moisture](https://www.amazon.com/dp/B094J8XD83?psc=1&ref=ppx_yo2ov_dt_b_product_details). These are connected to the analog input(s) of two different types of ESP devices. I am using [ESPHome](https://esphome.io/) to handle the initial setup and programming on these ESP devices.

The first device in use is an [ESP8266 Node Mini D1](https://www.amazon.com/dp/B081PX9YFV?psc=1&ref=ppx_yo2ov_dt_b_product_details). These only have one usable analog input and as such are going to be used around my home in places where there is only one plant.

The second device in use is an [ESP32-WROOM-32](https://www.amazon.com/dp/B09KRHNC6Z?psc=1&ref=ppx_yo2ov_dt_b_product_details). These have several usable analog inputs and as such are going to be used around my home in places where there are several plants in close proximity.

The sensors are designed to produce an output voltage of between 0 and ~ 3.0 V based on the relative moisture of the soil. In my testing, I am getting anywhere from 1.2 V (Dry) and 2.5 V (Wet).  After testing various plants around my home, both needing water and recently watered, I have decided upon a "trigger" voltage of 2.0 V. i.e if the sensor reads in > 2.0 V, it is time to water.  The onboard LED is a convenient "local" indicator and I turn it on when sensor is triggered to indicate the plant needs watered. In addition, this voltage is fed into the [Home Assistant Plant Monitor](https://www.home-assistant.io/integrations/plant/) to allow it to fully integrate with Home Assistant.

