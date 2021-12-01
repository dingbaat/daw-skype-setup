# DAW into Skype
Pipe playback from DAW directly into Skype.

**Prerequisites**
- Synchronous Audio Router
- DAW (Reaper / Ardour etc.)
- ASIO Driver

## Synchronous Audio Router

Download and install Synchronous Audio Router (SAR): http://sar.audio/

## Configure SAR in DAW (Ardour 6)

Download and install Ardour 6: https://ardour.org/whatsnew.html
Setup a new project in Ardour and make sure to choose the **Advanced Session**.
![enter image description here](https://raw.githubusercontent.com/dingbaat/daw-skype-setup/main/ardour-1.png)

Make sure that the selected *Driver* is **ASIO** and that the *Input* and *Output Device* are set to **Synchronous Audio Router**. Click on **Device Control Panel** to bring up to settings for SAR.
![enter image description here](https://raw.githubusercontent.com/dingbaat/daw-skype-setup/main/ardour-2.png)

The *Hardware Interface* should be set to the ASIO Driver of your Audio Interface. If you're not using an Audio Interface install and use **ASIO 4 ALL** as a fallback: https://www.asio4all.org/.

Now add a virtual **Recording** audio device which will pipe audio into Skype (or any other program). Apply the settings and start the session.

## Configure DAW (Ardour 6)
In your DAW create audio tracks for your microphone and instrument inputs and adjust the routing according to your hardware inputs. Add VSTs or onboard effects to your liking. 

Now create a bus to sum all the audio tracks we want to pipe into Skype. Set all those tracks as inputs on the newly created bus. Additionally set the outputs of that bus to the virtual audio device we've created in SAR.
![enter image description here](https://raw.githubusercontent.com/dingbaat/daw-skype-setup/main/ardour-5.png)

Here an example of a guitar track which is used as an input on our bus. The guitar track has **BIAS FX 2** as an external VST and the input is routed from our audio interface and the output is routed to our bus.
![enter image description here](https://raw.githubusercontent.com/dingbaat/daw-skype-setup/main/ardour-4.png)

## Setup Skype
Now we only need to use the output from our virtual audio device as an input in Skype.
![enter image description here](https://raw.githubusercontent.com/dingbaat/daw-skype-setup/main/ardour-6.png)
