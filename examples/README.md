# Examples

Hello, this directory contains some examples to help you get to grips with programming Ohbot. 

***Don't forget if you are new to Python here is a short guide explaining some of the key concepts:*** [Programming Ohbot in Python](https://docs.google.com/document/d/e/2PACX-1vTM9FmTBpGGJ4Ddvutpv3kxXkS0oyT4U9JPBV95UXdSJU10TD5JC1XWTf2cRGjHWApHOrTC6JLizD64/pub)

All the functions in the ohbot library are also documented if you scroll down in the main [README](https://github.com/ohbot/ohbot-python/blob/master/README.md).

Run an example
-

1) Right click and select save as on one of the files below.

2) Open and run in IDLE or whatever Python editor/launcher you prefer. 

[helloWorldOhbot.py](https://raw.githubusercontent.com/ohbot/ohbot-python/master/examples/helloWorldOhbot.py)
-
A simple program that makes Ohbot move and speak. 

 [threadingExample.py](https://raw.githubusercontent.com/ohbot/ohbot-python/master/examples/threadingExample.py)
-
A more slightly more complicated program that uses threads to make Ohbot do more than one thing at a time. 

[movementExample](https://raw.githubusercontent.com/ohbot/ohbot-python/master/examples/movementExample.py)
-
A step by step explanation of how to use the ohbot.move() function. Read through the script before running to see how it works. 

 [lightsAndSounds.py](https://raw.githubusercontent.com/ohbot/ohbot-python/master/examples/lightsAndSounds.py)
-
A program that demonstrates how to play sounds using ohbot.playSound()

[simpleMouseAndKeyboard.py](https://raw.githubusercontent.com/ohbot/ohbot-python/master/examples/simpleMouseAndKeyboard.py)
-
Control Ohbot's motor positions using the mouse and trigger actions using the a, b or c key on keyboard. 

 [ohClock.py](https://raw.githubusercontent.com/ohbot/ohbot-python/master/examples/ohClock.py)
-
This program makes Ohbot wake up every quarter of an hour and say the time. It also uses a second thread to blink Ohbot's eyes.  

 [wolframAlphaOhbot](https://raw.githubusercontent.com/ohbot/ohbot-python/master/examples/wolframAlphaOhbot.py)
-
This program uses the wolfram alpha and wikipedia web services to get definitions of words users type in. It builds upon the movements from the threadingExample. 

Requires:

Mac and Pi:

```sudo pip3 install wolframalpha```  

```sudo pip3 install wikipedia``` 

Windows:

```pip install wolframalpha```  

```pip install wikipedia``` 

Voice Examples
-
The examples demonstrating how to use different voices are platform specific so have been split into folders:

* [Mac Voice Examples](https://github.com/ohbot/ohbot-python/tree/master/examples/Mac)
* [Windows Voice Examples](https://github.com/ohbot/ohbot-python/tree/master/examples/Windows)
* [Pi Voice Examples](https://github.com/ohbot/ohbot-python/tree/master/examples/Pi)

