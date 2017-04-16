# ohbot for python

ohbot
========================

This package is a starting point for people wanting to use Python 3 to control Ohbot. 

More information about Ohbot can be found on: ohbot.co.uk

Dependencies
----------

Ohbot requires the following libraries be installed:


<table>
<tr>
<b>
<td>Library</td>
<td>Use</td>
<td>Terminal command to install</td>
<td>Link</td>
</b>
</tr>
<tr>
<td>ohbot</td>
<td>Interface with Ohbot</td>
<td>sudo pip3 install ohbot</td>
<td>https://github.com/ohbot/ohbot/</td>
</tr>
<tr>
<td>serial</td>
<td>Communicate with serial port</td>
<td>sudo pip3 install pyserial</td>
<td>https://github.com/pyserial/pyserial/</td>
</tr>
<tr>
<td>fesitival</td>
<td>Generate text to speech</td>
<td>sudo apt-get install festival</td>
<td>-</td>
</tr>
<tr>
<td>lxml</td>
<td>Import settings file</td>
<td>sudo apt-get install python3-lxml</td>
<td>https://github.com/lxml/lxml</td>
</tr>
<tr>
<td>threading</td>
<td>Run multiple threads</td>
<td>core</td>
<td>-</td>
</tr>
<tr>
<td>os</td>
<td>Send commands to festival</td>
<td>core</td>
<td>-</td>
</tr>
<tr>
<td>time</td>
<td>Run timers</td>
<td>core</td>
<td>-</td>
</tr>
</table>

Ohbot is tested with Python 3 running on a Raspberry Pi 3 Model B. 


Ohbot library files: (these will be installed with the pip3 command above)

<table>
<tr>
<b>
<td>ohbot.py</td>
<td>Ohbot package</td>
</b>
</tr>
<tr>
<td>MotorDefinionsv21.omd</td>
<td>Motor settings file.</td>
</tr>
</table>

<i> Note: The text to speech module Festival will generate an audio file, ‘ohbotspeech.wav’ and a text file ‘phonemes.txt’ inside your working folder. </i>

Hardware
-----

<u>Required:</u>


Raspberry Pi
<br>
Ohbot
<br>
USB Y Cable
<br>
USB Power Socket Adaptor
<br>
Speakers/headphones with 3.5mm headphone jack
<br>

<u>Setup:</u>



Plug the middle of USB Y cable into Raspberry Pi and the other large USB plug into the power adaptor. Then plug the mini USB into Ohbot. Finally plug your speakers into your Raspberry Pi. 


Writing Programs
--------

1.Open Python 3 (IDLE)
<br>
2.Click File → New File
<br>
3.Save your file as a python script (.py) in a new folder called Ohbot somewhere on your Pi.

Import
-------

Make sure you import ohbot at the start of your program. 
```python
From ohbot import ohbot
```

<br>

Functions
-------

ohbot.move(m,pos,speed = 3)
----------

<table>
<tr>
<td>Name</td>
<td>Range</td>
<td>Description</td>
<td>-</td>
</tr>
<tr>
<td>m</td>
<td>0-6(int)</td>
<td>Motor Number</td>
<td>-</td>
</tr>
<tr>
<td>pos</td>
<td>0-10(int)</td>
<td>Desired Position</td>
<td>-</td>
</tr>
<tr>
<td>speed</td>
<td>0-10(int)</td>
<td>Motor Speed</td>
<td>3</td>
</tr>
</table>


For Example:
```python
ohbot.move(1,7)

ohbot.move(2,3,1) 
```
Motor index reference:
<table>
<tr>
<td>m</td>
<td>0</td>
<td>1</td>
<td>2</td>
<td>3</td>
<td>4</td>
<td>5</td>
<td>6</td>
</tr>
<tr>
<td>motor</td>
<td>HeadNod</td>
<td>HeadTurn</td>
<td>EyeTurn</td>
<td>LidBlink</td>
<td>TopLip</td>
<td>BottomLip</td>
<td>EyeTurn</td>
</tr>

</table>

<br>

```python
ohbot.say(text,untilDone = True,lipSync = True)
```

----------

<table>
<tr>
<td>Name</td>
<td>Range</td>
<td>Description</td>
<td>Default</td>
</tr>
<tr>
<td>text</td>
<td>“A string with no punctuation”</td>
<td>Words to say</td>
<td>-</td>
</tr>
<tr>
<td>untilDone</td>
<td>bool</td>
<td>Return when finished speaking</td>
<td>True</td>
</tr>
<tr>
<td>lipSync</td>
<td>bool</td>
<td>Move lips in time with speech</td>
<td>True</td>
</tr>
</table>


For Example:
```python
ohbot.say(“Hello I am Ohbot”)

ohbot.say(“Goodbye”,False,False)
```


<br>

ohbot.wait(seconds)
----------

Seconds - float or int required wait time. ohbot.wait(1.5)

<table>
<tr>
<td>Name</td>
<td>Range</td>
<td>Description</td>
</tr>
<tr>
<td>seconds</td>
<td>float or int</td>
<td>Length of wait in seconds</td>
</tr>
</table>

For Example:
```python
ohbot.wait(2)

ohbot.wait(0.5)
```

<i>Note: It is important to use ohbot.wait() commands between motor sequential commands for the same motor. </i>

For Example:
```python
ohbot.move(1,7,2)

ohbot.wait(2)

ohbot.move(1,4,2)
```

<br>


ohbot.eyeColour(r,g,b)
----------

Set the colour of Ohbot’s eyes. 

<table>
<tr>
<td>Name</td>
<td>Range</td>
<td>Description</td>
</tr>
<tr>
<td>r</td>
<td>0-10(int)</td>
<td>Red</td>
</tr>
<tr>
<td>g</td>
<td>0-10(int)</td>
<td>Green</td>
</tr>
<tr>
<td>b</td>
<td>0-10(int)</td>
<td>Blue</td>
</tr>
</table>

For Example:
```python
ohbot.eyeColour(2,3,8)
```

<br>

ohbot.reset()
----------

Resets Ohbot’s motors back to rest positions and turns off Ohbot’s eyes. Useful to start programs with this. 

For Example:
```python
ohbot.reset()
ohbot.move(1,7,2)
ohbot.wait(1)
ohbot.move(1,1)
...
```

<br>

ohbot.close()
----------

Call at the end of your program to detach Ohbot’s motors.

For Example:
```python
ohbot.move(1,7,2)
ohbot.wait(1)
ohbot.move(1,1)

ohbot.close()
```

<b><i>Press fn + f5 to run your program.



