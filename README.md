# Neopixel
ESP-32 Sketch 

Installed Arduino IDE on WIndows 10

Lessons learned
There are a lot of ESP32 dev boards out there - make sure you have the Pin Out Datasheet that is specific to your board

Don't start with the onboard LED blink example - there are so many ways to suffer issues such as:

      Your board only has one onboard led rather than two
  
      Your on-board led will not work if a Serial command (eg Serial.println) is placed within your sketch
  
      Your onboard led is inverse loaded (On when low, Off when high)
  
Start with an example that uses a simple led that you can mount on your breadboard. Remember to

      Press and hold the BOOT button on your dev board when you try to connect on upload


FASTLED 

Example sketches provided with the FASTLED library work great. Just remember to 

    Amend the parameters at the top of the sketch (LED_PIN, NUM_LEDs etc)
    
    Hook up the data pin to the right end of the neopixel strip
    
    Take the time to understand how the FASTLED pallet works 
    
WEBSERVER

Example sketch for creating a WebServer worked first time!

OK - So we have got working FASTLEDS sketches, a working WebServer, how difficult could it be for them to work together so that we have a WIFI controlled set of neopixels. Lets find out!

Well as it turns out, the FASTLED library does not serve as a good bed fellow with other libraries. The main cultprit being that FASTLED disables interupts whilst setting the neopixels which in turn causes unpredictable results when integrating two libraries. 

Which is where @JasonCoon comes in. He has been wrestling with these issues since I was knee high and has posted working examples of WIFI/BLE controlled neopixels on GitHub. So lets start with his code and see where it takes us . . . 

